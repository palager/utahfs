Setup Google Cloud Storage
--------------------------

1. Sign up for a [Google Cloud Storage](https://cloud.google.com/storage) account
   and go to the console.
2. Generate 8 bytes of randomness: `openssl rand -hex 8`. This will be the name
   of the bucket, although you can add some extra text to the beginning or end
   to help you identify the bucket in the future.
3. Create a bucket with the same name as the string you generated above, and set
   the name as `gcs-bucket-name` in your config.
4. In the GCS console, open the sidebar, open the "APIs & Services" dropdown,
   and click "Credentials." Click "Create Credentials" and choose "Service
   Account". Configure the account and click "Create." Give the "Storage Admin"
   permission and click "Continue." Once finished, choose "Create Key" with key
   type "JSON" and save the provided file to disk.
5. Ensure that a path to this file is given in the
   `GOOGLE_APPLICATION_CREDENTIALS` environment variable, either when the server
   process runs in multi-device mode, or when the client process runs in
   single-device mode.

Note that the configuration option set here is kept under a `storage-provider`
key.
