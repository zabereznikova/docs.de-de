---
title: "Gewusst wie: Zuweisen von Benutzerinformationen zu Gruppenverbindungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 7ce550d6-8f7c-4ea7-add8-5bc27a7b51be
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Gewusst wie: Zuweisen von Benutzerinformationen zu Gruppenverbindungen
[Codebeispiel](#tskhowtoassignuserinformationtogroupconnectionsanchor1)  
  
 Im folgenden Beispiel wird veranschaulicht, wie Benutzerinformationen zu den Gruppen\-Verbindungen zuweist und ausgegangen wird, dass die Anwendung Variablen den *Benutzernamen*, *das SecurelyStoredPassword* und *die Domäne* festlegen, bevor dieser Codeabschnitt aufgerufen wird und dass *Benutzername* eindeutig ist.  
  
### So Benutzerinformationen zu einer Gruppen\-Verbindung zuweisen  
  
1.  Erstellen Sie einen Verbindungsgruppennamen.  
  
    ```csharp  
    SHA1Managed Sha1 = new SHA1Managed();  
    Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
    String secureGroupName = Encoding.Default.GetString(updHash);  
    ```  
  
    ```vb  
    Dim Sha1 As New SHA1Managed()  
    Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
    Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
    ```  
  
2.  Erstellen Sie eine Anforderung für eine bestimmte URL.  Beispielsweise erstellt der folgende Code eine Anforderung für die URL `http://www.contoso.com.`  
  
    ```csharp  
    WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
    ```  
  
    ```vb  
    Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ```  
  
3.  Legen Sie die Anmeldeinformationen und die Verbindung GroupName für die Webanforderung fest, und rufen **GetResponse** , ein **WebResponse**\-Objekt abzurufen.  
  
    ```csharp  
    myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);   
    myWebRequest.ConnectionGroupName = secureGroupName;  
  
    WebResponse myWebResponse=myWebRequest.GetResponse();  
    ```  
  
    ```vb  
    myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
    myWebRequest.ConnectionGroupName = secureGroupName  
  
    Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
  
    ```  
  
4.  Nach Verwendung des WebRespose\-Objekts schließen Sie den Antwortdatenstrom.  
  
    ```csharp  
    MyWebResponse.Close();  
  
    ```  
  
    ```vb  
    MyWebResponse.Close()  
    ```  
  
 Beispiel  
  
```csharp  
// Create a connection group name.  
SHA1Managed Sha1 = new SHA1Managed();  
Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
String secureGroupName = Encoding.Default.GetString(updHash);  
  
// Create a request for a specific URL.  
WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
  
myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);   
myWebRequest.ConnectionGroupName = secureGroupName;  
  
WebResponse myWebResponse=myWebRequest.GetResponse();  
  
// Insert the code that uses myWebResponse.  
  
MyWebResponse.Close();  
  
```  
  
```vb  
' Create a secure group name.  
Dim Sha1 As New SHA1Managed()  
Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
  
' Create a request for a specific URL.  
Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
  
myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
myWebRequest.ConnectionGroupName = secureGroupName  
  
Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
  
' Insert the code that uses myWebResponse.  
MyWebResponse.Close()  
```  
  
## Siehe auch  
 [Verwalten von Verbindungen](../../../docs/framework/network-programming/managing-connections.md)   
 [Verbindungsgruppierung](../../../docs/framework/network-programming/connection-grouping.md)