<h1>Splunk Data Onboarding with Heavy Forwarder</h1>


<h2>Description</h2>
Ingesting data correctly is a foundational step in managing a Splunk Data Infrastructure.
If done correctly, data onboarding allows an admin to get the most value from various input logs across the entire Splunk Deployment.
In this simple project,i demostrate a walk-through of how to configure various settings in various configuration files to onboard data into a splunk platform.
A heavy forwarder is used in this project.The use case for a heavy forwarder include the 

<br />
<h2>Use Cases for Heavy Forwarders</h2>

- <b>A heavy forwarder may be required by some splunk apps,add-ons or input types (HEC,DBconnect)</b>
- <b>Supports complex event routing.</b>
- <b>Ability to anonymize, mask and manipulate data before 
forwarding to the indexers.</b>
- <b>Provides Splunkweb when needed unlike Universal Forwarders.</b>


<h2>Lab Environment Setup</h2>

- <b>3 t2micro EC2 Intances running in AWS</b> 
- <b>Windows 10 work station (21H2)</b>
- <b>MobaXterm SSH Client</b>
- <b>OpenSSL</b>
- <b>Bash</b>

<h2>Splunk Deployment Instances</h2>

- <b>Indexer - IDX</b> 
- <b>Search Head - SH</b>
- <b>Heavy Forwarder - HF</b>

<h2>Program walk-through:</h2>



<br />
Install and configure 3 Splunk  instances running in AWS with labels:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206923811-b9587533-e8e9-4ae4-820b-3dedf415c40d.png" height="80%" width="80%"/>
<br />
<br />
Configure an input.conf  file to monitor incoming raw data : <br/>
<img src="https://user-images.githubusercontent.com/112047285/206924055-b3a58de1-157b-4a96-a1d8-bbdeacc2c289.png" height="80%" width="80%"/>
<br />
<br />
Create an outputs.conf file in the HF to fordard data to the indexer:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206924212-1cc487ee-0242-48ab-9f7b-e97fd90caa8e.png" height="80%" width="80%"/>
<br />
<br />
Enable receiving on the indexer to receive the data from the HF:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206924341-eb68100d-8a49-4a72-9ca6-325760b2e835.png" height="80%" width="80%"/>
                                                             
<br />
<br />
Create and configure a props.conf file to manipulate the data with appropriate sourcetypes stanzas:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206924514-114fcceb-6ac3-4b38-bca3-c6a25c3f628b.png" height="80%" width="80%"/>
<br />
<br />

Verify the indexes are created using the splunkweb on the indexer:  <br/>
<img src="https://user-images.githubusercontent.com/112047285/206924724-eb96cc31-2df1-4421-b8f1-19f7d2837388.png" height="80%" width="80%"/>
<br />
<br />

Use the Search Head to search the indexes,verify configurations and ensure data is well onboarded as required: <br/>
<img src="https://user-images.githubusercontent.com/112047285/206926078-4b74f1d5-a1c5-425f-9f15-9ccb4f5385b8.png" height="80%" width="80%"/>
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!
