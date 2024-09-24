## Identifying Stale EBS Snapshots

In this example, we'll create a Lambda function that identifies EBS snapshots that are no longer associated with any active EC2 instance and deletes them to save on storage costs.

## Description:

The Lambda function fetches all EBS snapshots owned by the same account ('self') and also retrieves a list of active EC2 instances (running and stopped). For each snapshot, it checks if the associated volume (if exists) is not associated with any active instance. If it finds a stale snapshot, it deletes it, effectively optimizing storage costs.

Key Features:

1) Snapshot Identification: The Lambda function queries all EBS snapshots and checks whether each snapshot is linked to any active EC2 instance. It identifies orphaned snapshots that are no longer needed.

2) Automated Deletion: Once orphaned snapshots are identified, the Lambda function deletes them automatically, freeing up storage space and reducing associated costs.
  
3) Event-Driven Execution: This Lambda function can be triggered on a schedule using Amazon CloudWatch Events (or EventBridge), ensuring regular cleanup of unused EBS snapshots without manual intervention.
 
4) Cost Optimization: By automatically removing unnecessary EBS snapshots, this solution helps optimize storage usage and reduce long-term AWS costs.

## Sample ScreenShot

<img width="1440" alt="1 " src="https://github.com/user-attachments/assets/713fab88-de29-48e2-bd5a-1763f94e7249">
<img width="1440" alt="2" src="https://github.com/user-attachments/assets/2da1e390-7e2d-456d-86d4-4555e00d611a">
<img width="1440" alt="3" src="https://github.com/user-attachments/assets/3d0f096c-10a6-4246-b3e1-775ba2794950">
<img width="1440" alt="4" src="https://github.com/user-attachments/assets/3c259af2-a041-4b86-aacf-9499c81dd69d">
