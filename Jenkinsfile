@Library('commons-net') _
pipeline {
  agent any

  stages {
    stage('FTP Upload') {
      steps {
        script {
          // Define the FTP server details
          def server = 'smog.000.pe'
          def username = 'if0_34551591'
          def password = 'bEyn17o1bAC'
          def port = 21

          // Define the file details to be uploaded
        //   def localFile = 'path/to/local/file.txt'
          def localFile = "https://github.com/pavanpanchal1/exampl.git"

          def remoteDirectory = '/htdocs'

          // Connect to the FTP server
          def ftpClient = ftpConnect(server, username, password, port)

          // Upload the file
          ftpUpload(ftpClient, localFile, remoteDirectory)

          // Disconnect from the FTP server
          ftpDisconnect(ftpClient)
        }
      }
    }
  }
}

def ftpConnect(String server, String username, String password, int port) {
  def ftp = [:]
  ftp.client = new FTPClient()

  try {
    // Connect to the FTP server
    ftp.client.connect(server, port)
    ftp.client.login(username, password)
    ftp.client.enterLocalPassiveMode()

    // Check if the connection was successful
    if (!FTPReply.isPositiveCompletion(ftp.client.getReplyCode())) {
      error("Failed to connect to the FTP server.")
    }
  } catch (Exception e) {
    error("Failed to connect to the FTP server. Error: ${e.message}")
  }

  return ftp
}

def ftpUpload(ftp, String localFile, String remoteDirectory) {
  try {
    // Change the working directory on the FTP server
    ftp.client.changeWorkingDirectory(remoteDirectory)

    // Upload the file
    FileInputStream inputStream = new FileInputStream(localFile)
    ftp.client.storeFile(localFile.name, inputStream)
    inputStream.close()

    // Check if the file upload was successful
    if (!FTPReply.isPositiveCompletion(ftp.client.getReplyCode())) {
      error("Failed to upload the file to the FTP server.")
    }
  } catch (Exception e) {
    error("Failed to upload the file to the FTP server. Error: ${e.message}")
  }
}

def ftpDisconnect(ftp) {
  try {
    // Disconnect from the FTP server
    ftp.client.logout()
    ftp.client.disconnect()
  } catch (Exception e) {
    error("Failed to disconnect from the FTP server. Error: ${e.message}")
  }
}

pipeline {
  agent any

  stages {
    stage('FTP Upload') {
      steps {
        script {
          // Define the FTP server details
          def server = 'smog.000.pe'
          def username = 'if0_34551591'
          def password = 'bEyn17o1bAC'
          def port = 21

          // Define the file details to be uploaded
        //   def localFile = 'path/to/local/file.txt'
          def localFile = "https://github.com/pavanpanchal1/exampl.git"

          def remoteDirectory = '/htdocs'

          // Connect to the FTP server
          def ftpClient = ftpConnect(server, username, password, port)

          // Upload the file
          ftpUpload(ftpClient, localFile, remoteDirectory)

          // Disconnect from the FTP server
          ftpDisconnect(ftpClient)
        }
      }
    }
  }
}

def ftpConnect(String server, String username, String password, int port) {
  def ftp = [:]
  ftp.client = new FTPClient()

  try {
    // Connect to the FTP server
    ftp.client.connect(server, port)
    ftp.client.login(username, password)
    ftp.client.enterLocalPassiveMode()

    // Check if the connection was successful
    if (!FTPReply.isPositiveCompletion(ftp.client.getReplyCode())) {
      error("Failed to connect to the FTP server.")
    }
  } catch (Exception e) {
    error("Failed to connect to the FTP server. Error: ${e.message}")
  }

  return ftp
}

def ftpUpload(ftp, String localFile, String remoteDirectory) {
  try {
    // Change the working directory on the FTP server
    ftp.client.changeWorkingDirectory(remoteDirectory)

    // Upload the file
    FileInputStream inputStream = new FileInputStream(localFile)
    ftp.client.storeFile(localFile.name, inputStream)
    inputStream.close()

    // Check if the file upload was successful
    if (!FTPReply.isPositiveCompletion(ftp.client.getReplyCode())) {
      error("Failed to upload the file to the FTP server.")
    }
  } catch (Exception e) {
    error("Failed to upload the file to the FTP server. Error: ${e.message}")
  }
}

def ftpDisconnect(ftp) {
  try {
    // Disconnect from the FTP server
    ftp.client.logout()
    ftp.client.disconnect()
  } catch (Exception e) {
    error("Failed to disconnect from the FTP server. Error: ${e.message}")
  }
}
