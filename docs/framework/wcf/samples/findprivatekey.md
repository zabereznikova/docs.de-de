---
title: FindPrivateKey-Beispiel – WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: b89d135d7412f10cb9de1e4bda1aaab14b29cbf0
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490768"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="850d6-102">FindPrivateKey-Beispiel</span><span class="sxs-lookup"><span data-stu-id="850d6-102">FindPrivateKey sample</span></span>

<span data-ttu-id="850d6-103">Es kann schwierig sein, den Speicherort und Namen der Privatschlüsseldatei zu finden, die einem bestimmten X.509-Zertifikat im Zertifikatspeicher zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="850d6-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="850d6-104">Das Tool FindPrivateKey.exe erleichtert diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="850d6-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="850d6-105">FindPrivateKey ist ein Beispiel, das vor der Verwendung kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="850d6-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="850d6-106">Finden Sie unter den [das FindPrivateKey-Projekt erstellen](#to-build-the-findprivatekey-project) Abschnitt die Anweisungen zum Erstellen des Tools findprivatekey bereit.</span><span class="sxs-lookup"><span data-stu-id="850d6-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="850d6-107">X.509-Zertifikate werden von einem Administrator oder einem beliebigen Benutzer auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="850d6-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="850d6-108">Allerdings kann das Zertifikat von einem Dienst unter einem anderen Konto zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="850d6-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="850d6-109">Z. B. das NETZWERKDIENST-Konto.</span><span class="sxs-lookup"><span data-stu-id="850d6-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="850d6-110">Dieses Konto verfügt möglicherweise nicht über Zugriff auf die Privatschlüsseldatei, da das Zertifikat nicht ursprünglich von diesem Konto installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="850d6-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="850d6-111">Das Tool FindPrivateKey gibt den Speicherort der Privatschlüsseldatei eines X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="850d6-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="850d6-112">Sie können Berechtigungen in dieser Datei hinzufügen oder entfernen, wenn Sie den Speicherort der Privatschlüsseldatei der jeweiligen X.509-Zertifikate kennen.</span><span class="sxs-lookup"><span data-stu-id="850d6-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="850d6-113">Die Beispiele, die Zertifikate für die Sicherheit zu verwenden, verwenden das Tool FindPrivateKey in der *"Setup.bat"* Datei.</span><span class="sxs-lookup"><span data-stu-id="850d6-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="850d6-114">Sobald eine Datei mit die private Schlüssel gefunden wurde, können Sie andere Tools wie z. B. *Cacls.exe* die richtigen Zugriffsrechte auf die Datei festlegen.</span><span class="sxs-lookup"><span data-stu-id="850d6-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="850d6-115">Stellen Sie sicher, dass das Benutzerkonto, das nur-Lese Zugriff auf die Datei hat, wenn ein Windows Communication Foundation (WCF)-Dienst unter einem Benutzerkonto, z. B. einen selbst gehosteten ausführbaren Datei, ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="850d6-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="850d6-116">Bei der Ausführung eines WCF-Diensts unter Internet Information Services (IIS) sind die Standardkonten, denen der Dienst ausgeführt, klicken Sie unter wird der Netzwerkdienst in IIS 7 und früheren Versionen oder Identität des Anwendungspools in IIS 7.5 und höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="850d6-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="850d6-117">Weitere Informationen finden Sie unter [Anwendungspoolidentitäten](/iis/manage/configuring-security/application-pool-identities).</span><span class="sxs-lookup"><span data-stu-id="850d6-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="850d6-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="850d6-118">Examples</span></span>

<span data-ttu-id="850d6-119">Beim Zugriff auf ein Zertifikat für die der Prozess Leseberechtigung keine Ausnahmemeldung ähnlich wie im folgenden Beispiel angezeigt:</span><span class="sxs-lookup"><span data-stu-id="850d6-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="850d6-120">In diesem Fall verwenden Sie das FindPrivateKey-Tool, um eine Datei mit dem privaten Schlüssel zu suchen, und legen Sie dann die Zugriffsberechtigung für den Prozess, unter der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="850d6-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="850d6-121">Beispielsweise kann dies mit dem Tool Cacls.exe erfolgen wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="850d6-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="850d6-122">So erstellen Sie das FindPrivateKey-Projekt</span><span class="sxs-lookup"><span data-stu-id="850d6-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="850d6-123">Um das Projekt herunterzuladen, besuchen Sie [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span><span class="sxs-lookup"><span data-stu-id="850d6-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="850d6-124">Öffnen Sie den Datei-Explorer, und navigieren Sie zu der *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* Ordner, in dem Verzeichnis, in dem Sie das Beispiel installiert haben.</span><span class="sxs-lookup"><span data-stu-id="850d6-124">Open File Explorer and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="850d6-125">Doppelklicken Sie auf das Symbol für die SLN-Datei, um diese in Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="850d6-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="850d6-126">In der **erstellen** , wählen Sie im Menü **Projektmappe neu erstellen**.</span><span class="sxs-lookup"><span data-stu-id="850d6-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="850d6-127">Erstellen der Projektmappe generiert die Datei: FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="850d6-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="850d6-128">Konventionen: befehlszeileneinträge</span><span class="sxs-lookup"><span data-stu-id="850d6-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="850d6-129">"[*Option*]" stellt einen optionalen Satz von Parametern.</span><span class="sxs-lookup"><span data-stu-id="850d6-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="850d6-130">"{*Option*}" stellt einen obligatorischen Satz von Parametern.</span><span class="sxs-lookup"><span data-stu-id="850d6-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="850d6-131">"*option1* &#124; *option2*" eine Wahl zwischen Gruppen von Optionen darstellt.</span><span class="sxs-lookup"><span data-stu-id="850d6-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="850d6-132">"\<*Wert*>" stellt einen Parameterwert eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="850d6-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="850d6-133">Verwendung</span><span class="sxs-lookup"><span data-stu-id="850d6-133">Usage</span></span>

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="850d6-134">Ort:</span><span class="sxs-lookup"><span data-stu-id="850d6-134">Where:</span></span>

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

<span data-ttu-id="850d6-135">Wenn keine Parameter an der Eingabeaufforderung angegeben werden, wird dann dieser Text angezeigt.</span><span class="sxs-lookup"><span data-stu-id="850d6-135">If no parameters are specified at the command prompt, then this help text is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="850d6-136">Beispiele</span><span class="sxs-lookup"><span data-stu-id="850d6-136">Examples</span></span>

<span data-ttu-id="850d6-137">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragstellernamen "CN = Localhost", im persönlichen Speicher des aktuellen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="850d6-137">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="850d6-138">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragstellernamen "CN = Localhost" im persönlichen Speicher des aktuellen Benutzers und den vollständigen Verzeichnispfad ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="850d6-138">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="850d6-139">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Fingerabdruck "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" im persönlichen Speicher des lokalen Computers gesucht.</span><span class="sxs-lookup"><span data-stu-id="850d6-139">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
