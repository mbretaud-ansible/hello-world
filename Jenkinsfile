node("slave") {

    def phenixHttpProxy = "${env.PHENIX_HTTP_PROXY}"
    def phenixHttpsProxy = "${env.PHENIX_HTTPS_PROXY}"
    def phenixFtpProxy = "${env.PHENIX_FTP_PROXY}"
    def phenixNoProxy = "${env.PHENIX_NO_PROXY}"

    phenixJob {
        project = "phenix-ops"
        recipient = "Phenix_Core@carrefour.com"

        body = {
            withEnv([
                    "http_proxy=${phenixHttpProxy}",
                    "https_proxy=${phenixHttpsProxy}",
                    "ftp_proxy=${phenixFtpProxy}",
                    "no_proxy=${phenixNoProxy}"
            ]) {

                stage "Publish"
                sh 'make push'
            }
        }
        finallyBody = {
        }
    }
}