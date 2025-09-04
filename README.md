# Prerequisites 
 A reddit account  
    &nbsp;&nbsp;- To use it api<br/>
    
 A Google cloud account  
    &nbsp;&nbsp;- To use its Vision AI API  

# To Run Code in Colab
1. Open the <code> data_collector.ipynb </code> file in Google Colab
2. Upload <code> Requirement.txt </code>, Google Cloud's Vision AI Service key which will be a <code> .json </code> file in **/content/** folder in google colab
3. Start Session and Run all the cells 


# Getting Reddit API Credentials

Follow these steps to generate Reddit API credentials for your project:

1. Go to [Reddit App Preferences](https://www.reddit.com/prefs/apps) (log in if required).
2. Scroll down to **Developed Applications** and click **Create App** or **Create Another App**.
3. Fill in the application details:
   - **Name**: Choose any name (e.g., `MyScraper`).
   - **Type**: Select **script** (for personal use).
   - **Redirect URI**: Use `http://localhost:8080` (or any valid URL).
   - **Description**: Optional, can be left blank.
4. Click **Create app**.
5. Once created, you will see:
   - **Client ID** → the 14-character string under your app name.
   - **Client Secret** → displayed right below it.
6. Keep these values safe. You will also need:
   - Your **Reddit username**
   - Your **Reddit password**
7. Use these credentials in your code for authentication.

---
✅ Example environment variables setup:

```env
REDDIT_CLIENT_ID=your_client_id_here
REDDIT_CLIENT_SECRET=your_client_secret_here
REDDIT_USERNAME=your_username
REDDIT_PASSWORD=your_password
REDDIT_USER_AGENT=your_app_name
# Getting Google Cloud Vision API Credentials
```
# Getting Google Cloud Vision API Credentials
Follow these steps to generate a service account key for Google Cloud Vision API:

1. Go to the [Google Cloud Console](https://console.cloud.google.com/).
2. Create a new project or select an existing one.
3. Enable the **Vision API**:
   - In the sidebar, go to **APIs & Services > Library**.
   - Search for **Vision API** and click **Enable**.
4. Create service account credentials:
   - Go to **APIs & Services > Credentials**.
   - Click **Create Credentials > Service Account**.
5. Enter a service account name, then assign a role (e.g., **Editor** or a custom role with Vision API access).
6. After creating the service account, open it and go to the **Keys** tab.
7. Click **Add Key > Create New Key** → select **JSON** → **Create**.
8. A `.json` key file will be downloaded to your computer. This is your **service account key**.



```bash
credentials = service_account.Credentials.from_service_account_file("/content/chat-image-detector-b43386af8be8.json")

