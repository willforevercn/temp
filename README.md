# temp
    @Test
    public void setSaveCredential() {
        File file = new File("/fake/client_bundle.pk12");
        FileInputStream fin = null;
        byte[] credentialBinary = null;
        try {
            fin = new FileInputStream(file);
            credentialBinary = new byte[(int) file.length()];
            fin.read(credentialBinary);
        } catch (Throwable e) {

        }

        String base64EncodedCredential = Base64.encodeAsString(credentialBinary);

        CredentialManager.getInstance().saveCredential(CredentialType.CANONICAL_PROFILE_CERT,
                base64EncodedCredential);
    }

