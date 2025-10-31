## Storage Classes

Amazon S3 offers multiple storage classes, each designed for specific use cases:

| Storage Class | Purpose |
| **Standard** | Frequently accessed data, high availability, low latency |
| **Standard-IA (Infrequent Access)** | Data accessed occasionally, lower cost, retrieval fees apply |
| **Glacier** | Long-term archival, very low cost, retrieval takes minutes or hours |

---

**Steps Followed:**
1. Created three sample files: `file-standard.txt`, `file-ia.txt`, `file-glacier.txt`.  
2. Uploaded them to my bucket: `chistudent-s3-assignment`.  
3. Assigned each file the appropriate storage class via the **Actions → Change storage class** option in the S3 Console.  
4. Verified storage classes in the **Objects** list.

---

## Versioning

Versioning allows S3 to keep multiple versions of the same object, which is useful for recovery and auditing.

**Steps Followed:**
1. Enabled **versioning** on the bucket: `chistudent-s3-assignment`.  
2. Uploaded `index.html` (original) → Version 1.  
3. Edited local `index.html` (changed `<h1>` text to “Version 2”) → Uploaded → Version 2.  
4. Verified both versions in **Objects → index.html → Versions**, showing unique Version IDs.  
5. Optionally restored the old version by downloading Version 1 and re-uploading it.

---

## Cross-Region Replication 

Replication automatically copies objects from a source bucket to a destination bucket in another region.

**Steps Followed:**
1. Created a **destination bucket** in `eu-west-1`
2. Enabled versioning on the destination bucket.  
3. Configured **Replication Rule** on the source bucket:
   - Applied to all new objects  
   - Created an IAM role via the console for S3 to replicate objects  
   - Chose **Do not replicate existing objects**  
4. Tested replication by uploading `replication-test.txt` to the source bucket.  
   - File appeared automatically in the destination bucket after a few minutes.


## Shared Responsibility Model for S3

Amazon Web Services uses a **Shared Responsibility Model** for cloud security:

**AWS Responsibilities:**
- Maintaining the physical infrastructure, servers, and data centers  
- Ensuring network security and availability  
- Providing durability and redundancy for data stored in S3  
