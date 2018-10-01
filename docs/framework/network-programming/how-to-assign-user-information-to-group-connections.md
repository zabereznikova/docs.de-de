---
title: 'Gewusst wie: Zuweisen von Benutzerinformationen zu Gruppenverbindungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ce550d6-8f7c-4ea7-add8-5bc27a7b51be
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 009c23d0015f366ab5f1ee92609f0131465d827b
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47193098"
---
# <a name="how-to-assign-user-information-to-group-connections"></a><span data-ttu-id="ee9c3-102">Gewusst wie: Zuweisen von Benutzerinformationen zu Gruppenverbindungen</span><span class="sxs-lookup"><span data-stu-id="ee9c3-102">How to: Assign User Information to Group Connections</span></span>

  
 <span data-ttu-id="ee9c3-103">Das folgende Beispiel demonstriert, wie Benutzerinformationen zu Gruppenverbindungen zugewiesen werden können. Dabei wird angenommen, dass die Anwendung die Variablen *UserName*, *SecurelyStoredPassword* und *Domain* vor dem Aufrufen dieses Codeabschnitts festgelegt hat und dass *UserName* eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="ee9c3-103">The following example demonstrates how to assign user information to group connections, assuming that the application sets the variables *UserName*, *SecurelyStoredPassword*, and *Domain* before this section of code is called and that *UserName* is unique.</span></span>  
  
### <a name="to-assign-user-information-to-a-group-connection"></a><span data-ttu-id="ee9c3-104">Zuweisen von Benutzerinformationen zu Gruppenverbindungen</span><span class="sxs-lookup"><span data-stu-id="ee9c3-104">To assign user information to a group connection</span></span>  
  
1.  <span data-ttu-id="ee9c3-105">Erstellen Sie einen Verbindungsgruppennamen.</span><span class="sxs-lookup"><span data-stu-id="ee9c3-105">Create a connection group name.</span></span>  
  
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
  
2.  <span data-ttu-id="ee9c3-106">Erstellen Sie eine Anforderung für eine bestimmte URL.</span><span class="sxs-lookup"><span data-stu-id="ee9c3-106">Create a request for a specific URL.</span></span> <span data-ttu-id="ee9c3-107">Im folgenden Code wird z.B. eine Anforderung für die URL `http://www.contoso.com.` erstellt.</span><span class="sxs-lookup"><span data-stu-id="ee9c3-107">For example, the following code creates a request for the URL `http://www.contoso.com.`</span></span>  
  
    ```csharp  
    WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
    ```  
  
    ```vb  
    Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ```  
  
3.  <span data-ttu-id="ee9c3-108">Legen Sie die Anmeldeinformationen und den Verbindungsgruppennamen für die Web-Anforderung fest, und rufen Sie **GetResponse** auf, um ein **WebResponse**-Objekt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee9c3-108">Set the credentials and Connection GroupName for the Web request, and call **GetResponse** to retrieve a **WebResponse** object.</span></span>  
  
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
  
4.  <span data-ttu-id="ee9c3-109">Schließen Sie den Antwortstream nach dem Verwenden des „WebResponse“-Objekts.</span><span class="sxs-lookup"><span data-stu-id="ee9c3-109">Close the response stream after using the WebRespose object.</span></span>  
  
    ```csharp  
    MyWebResponse.Close();  
    ```  
  
    ```vb  
    MyWebResponse.Close()  
    ```  
  
 <span data-ttu-id="ee9c3-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee9c3-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ee9c3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee9c3-111">See Also</span></span>  
 [<span data-ttu-id="ee9c3-112">Verwalten von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="ee9c3-112">Managing Connections</span></span>](../../../docs/framework/network-programming/managing-connections.md)  
 [<span data-ttu-id="ee9c3-113">Connection Grouping (Verbindungsgruppierung)</span><span class="sxs-lookup"><span data-stu-id="ee9c3-113">Connection Grouping</span></span>](../../../docs/framework/network-programming/connection-grouping.md)
