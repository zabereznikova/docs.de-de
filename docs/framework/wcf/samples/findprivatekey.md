---
title: FindPrivateKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c1ff00bead6130601070ac94686ee9622a6fe218
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="findprivatekey"></a><span data-ttu-id="c213c-102">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="c213c-102">FindPrivateKey</span></span>
<span data-ttu-id="c213c-103">Es kann schwierig sein, den Speicherort und Namen der Privatschlüsseldatei zu finden, die einem bestimmten X.509-Zertifikat im Zertifikatspeicher zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c213c-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="c213c-104">Das Tool FindPrivateKey.exe erleichtert diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="c213c-104">The FindPrivateKey.exe tool facilitates this process.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c213c-105">FindPrivateKey ist ein Beispiel, das vor der Verwendung kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="c213c-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="c213c-106">Zum Erstellen Sie das FindPrivateKey-Tool finden Sie unter "So erstellen Sie das FindPrivateKey-Projekt" unten im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="c213c-106">See the "To build the FindPrivateKey project" section below for instructions on how to build the FindPrivateKey tool.</span></span>  
  
 <span data-ttu-id="c213c-107">X.509-Zertifikate werden von einem Administrator oder einem beliebigen Benutzer auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c213c-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="c213c-108">Auf das Zertifikat kann jedoch von einem Dienst zugegriffen werden, der unter einem anderen Konto ausgeführt wird (beispielsweise ASPNET unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] oder die NETWORK SERVICE-Konten unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="c213c-108">However the certificate may be accessed by a service running under a different account (for example, the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE accounts on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span></span>  
  
 <span data-ttu-id="c213c-109">Dieses Konto verfügt möglicherweise nicht über Zugriff auf die Privatschlüsseldatei, da das Zertifikat nicht ursprünglich von diesem Konto installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="c213c-109">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="c213c-110">Das Tool FindPrivateKey gibt den Speicherort der Privatschlüsseldatei eines X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="c213c-110">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="c213c-111">Sie können Berechtigungen in dieser Datei hinzufügen oder entfernen, wenn Sie den Speicherort der Privatschlüsseldatei der jeweiligen X.509-Zertifikate kennen.</span><span class="sxs-lookup"><span data-stu-id="c213c-111">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>  
  
 <span data-ttu-id="c213c-112">In den Beispielen, in denen Zertifikate für die Sicherheit verwendet werden, wird das Tool FindPrivateKey in der Datei "Setup.bat" verwendet.</span><span class="sxs-lookup"><span data-stu-id="c213c-112">The samples that use certificates for security use the FindPrivateKey tool in the Setup.bat file.</span></span> <span data-ttu-id="c213c-113">Wenn die Privatschlüsseldatei gefunden wurde, können Sie mit anderen Tools wie Cacls.exe die entsprechenden Zugriffsrechte für die Datei festlegen.</span><span class="sxs-lookup"><span data-stu-id="c213c-113">Once the private key file has been found you can use other tools such as Cacls.exe to set the appropriate access rights onto the file.</span></span>  
  
 <span data-ttu-id="c213c-114">Stellen Sie beim Ausführen eines [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Diensts unter einem Benutzerkonto sicher, beispielsweise einer selbst gehosteten ausführbaren Datei, dass das Benutzerkonto nur über Lesezugriff auf die Datei verfügt.</span><span class="sxs-lookup"><span data-stu-id="c213c-114">When running a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="c213c-115">Beim Ausführen eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts unter Internetinformationsdienste (IIS) lauten die Standardkonten, unter denen der Dienst ausgeführt wird, ASPNET unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] bzw. NETWORK SERVICE unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]. Diese verfügen standardmäßig nicht über Zugriff auf die Privatschlüsseldatei.</span><span class="sxs-lookup"><span data-stu-id="c213c-115">When running a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under Internet Information Services (IIS) the default accounts that the service runs under are the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], which by default do not have access to the private key file.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c213c-116">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c213c-116">Examples</span></span>  
 <span data-ttu-id="c213c-117">Beim Zugreifen auf ein Zertifikat, für das der Prozess über keine Leseberechtigung verfügt, wird eine Ausnahmemeldung angezeigt, ähnlich wie im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c213c-117">When accessing a certificate for which the process does not have read privilege, you see an exception message similar to the following example.</span></span>  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 <span data-ttu-id="c213c-118">Wenn dies auftritt, suchen Sie mithilfe des Tools FindPrivateKey die Privatschlüsseldatei, und legen Sie dann die Zugriffsberechtigung für den Prozess fest, unter dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c213c-118">When this occurs use the FindPrivateKey tool to find the private key file and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="c213c-119">Dies kann beispielsweise mit dem Tool Cacls.exe erfolgen, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c213c-119">For example, this can be done with the Cacls.exe tool as shown in the following example.</span></span>  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="c213c-120">So erstellen Sie das FindPrivateKey-Projekt</span><span class="sxs-lookup"><span data-stu-id="c213c-120">To build the FindPrivateKey project</span></span>  
  
1.  <span data-ttu-id="c213c-121">Öffnen Sie [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], und navigieren Sie zum sprachspezifischen Unterverzeichnis im Verzeichnis, in dem Sie das Beispiel installiert haben.</span><span class="sxs-lookup"><span data-stu-id="c213c-121">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>  
  
2.  <span data-ttu-id="c213c-122">Doppelklicken Sie auf das Symbol für die SLN-Datei, um diese in Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c213c-122">Double-click the .sln file icon to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="c213c-123">In der **erstellen** klicken Sie im Menü **Projektmappe neu erstellen**.</span><span class="sxs-lookup"><span data-stu-id="c213c-123">In the **Build** menu, select **Rebuild Solution**.</span></span> <span data-ttu-id="c213c-124">Die Clientprogrammdateien werden im Verzeichnis client\bin erstellt, und die Dienstprogrammdateien werden im Verzeichnis service\bin erstellt.</span><span class="sxs-lookup"><span data-stu-id="c213c-124">The client program files are built to client\bin and the service program files are built to service\bin.</span></span>  
  
4.  <span data-ttu-id="c213c-125">Beim Erstellen der Projektmappe wird die Datei "FindPrivateKey.exe" erstellt.</span><span class="sxs-lookup"><span data-stu-id="c213c-125">Building the solution generates the file: FindPrivateKey.exe.</span></span>  
  
## <a name="conventionscommand-line-entries"></a><span data-ttu-id="c213c-126">Konventionen: Befehlszeileneinträge</span><span class="sxs-lookup"><span data-stu-id="c213c-126">Conventions—Command-Line Entries</span></span>  
 <span data-ttu-id="c213c-127">"[*Option*]" stellt einen optionalen Satz von Parametern dar.</span><span class="sxs-lookup"><span data-stu-id="c213c-127">"[*option*]" represents an optional set of parameters.</span></span>  
  
 <span data-ttu-id="c213c-128">"{*Option*}" stellt einen obligatorischen Satz von Parametern dar.</span><span class="sxs-lookup"><span data-stu-id="c213c-128">"{*option*}" represents a mandatory set of parameters.</span></span>  
  
 <span data-ttu-id="c213c-129">"*option1* &#124; *option2*"stellt eine Auswahl zwischen Sätzen von Optionen dar.</span><span class="sxs-lookup"><span data-stu-id="c213c-129">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>  
  
 <span data-ttu-id="c213c-130">"\<*Wert*>" stellt einen Parameterwert eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c213c-130">"\<*value*>" represents a parameter value to be entered.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="c213c-131">Verwendung</span><span class="sxs-lookup"><span data-stu-id="c213c-131">Usage</span></span>  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 <span data-ttu-id="c213c-132">Wobei:</span><span class="sxs-lookup"><span data-stu-id="c213c-132">Where:</span></span>  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 <span data-ttu-id="c213c-133">Wenn keine Parameter bei der Eingabeaufforderung angegeben werden, wird dieser Hilfetext angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c213c-133">If no parameters are specified at the command prompt then this help text is displayed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c213c-134">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c213c-134">Examples</span></span>  
 <span data-ttu-id="c213c-135">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragstellernamen "CN=localhost" im persönlichen Speicher des aktuellen Benutzers gesucht.FindPrivateKey My CurrentUser -n "CN=localhost".</span><span class="sxs-lookup"><span data-stu-id="c213c-135">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.FindPrivateKey My CurrentUser -n "CN=localhost".</span></span>  
  
 <span data-ttu-id="c213c-136">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragstellernamen "CN=localhost" im persönlichen Speicher des aktuellen Benutzers gesucht und der vollständige Verzeichnispfad ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="c213c-136">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current and output the full directory path.</span></span>  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
```  
  
 <span data-ttu-id="c213c-137">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Fingerabdruck "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" im persönlichen Speicher des lokalen Computers gesucht.</span><span class="sxs-lookup"><span data-stu-id="c213c-137">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## <a name="see-also"></a><span data-ttu-id="c213c-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c213c-138">See Also</span></span>
