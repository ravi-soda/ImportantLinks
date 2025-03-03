Platinum code improvements.
 
 
SQL
const ppipHandler = () => {
    const batchParams = await prepareBatchParameters: () => {
        await fetchMaxOfLastAggregatedTimeStampForStreams()
        await fetchTotalPpipRecordsToProcess()
    }
    const auditRecord = await createAuditTable();
    const ppipRecords = await fetchPpipRecordsToProcess(batchParams);
    const ppipRecordsToSync (insert,update,oneToMany) = applyBizRules(ppipRecords);
    await createBulkJob(ppipRecordsToSync (insert/update));
    await reportOneToManyToStream(ppipRecordsToSync.oneToMany);
    await updateAuditTable(auditRecord);
}
1. DQ testing report
2. Test cases/coverage of important methods.
	- fetch services
	- PPG flow business logic code.
3. Grafana logs audit and Alert
4. Batch job auditing
	- property
	- rent
	- loan
	- sales
5. Changes needed for the auditing of bulkJob result to Stream
	-- prepare batch job inputs --
{ batch job params } --> batch job wrapper layer --
	 .. fetch batch job to run ..
	 .. divide the data into chunks ..
{ chunk params } --> process data chunk Extracting, transforming and loading (ETL)  --
	 .. fetch chunk data ..
	 .. process chunk data ..
		.. filter 
	 .. prepare transformed data ..
	 .. sync the data to SF ..
	-- Audit results --
	 .. audit results to db ..
	 .. audit results to msg store ..

Batch Job Phases
Each time a Batch Job component executes, the following phases take place:
Load and Dispatch Phase: The Batch Job component splits valid input into records and prepares the records for processing. This phase takes place within the Batch Job component.
Process Phase: Mule components and connector operations within one or more Batch Step components in the Batch Job process records within a given batch job instance. Processing within a Batch Aggregator component also occurs in the Process phase.
On Complete Phase: The Batch Job component issues a report object with the result of processing the batch job instance.
https://docs.mulesoft.com/mule-runtime/latest/batch-filters-and-batch-aggregator
 
Filtering Records to Process within a Batch Step Component
Performing Bulk Operations from a Batch Aggregator Component
Modifying Records within a Batch Aggregator
Preserving the MIME types of the Aggregated Records
Changing the Record Block Size
Setting a Max Concurrency Limit on Batch Job Instances
Batch Job Component (<batch:job />)
Batch Step Component (<batch:step/>)
Batch Aggregator Component (<batch:aggregator />)
 
 
