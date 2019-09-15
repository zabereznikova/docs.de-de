---
title: FindPrivateKey-Beispiel-WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 4ba4316489c1494da9421bea5c513e44c6eb50a7
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989886"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="f925d-102">FindPrivateKey-Beispiel</span><span class="sxs-lookup"><span data-stu-id="f925d-102">FindPrivateKey sample</span></span>

<span data-ttu-id="f925d-103">Es kann schwierig sein, den Speicherort und Namen der Privatschlüsseldatei zu finden, die einem bestimmten X.509-Zertifikat im Zertifikatspeicher zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f925d-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="f925d-104">Das Tool FindPrivateKey.exe erleichtert diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="f925d-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f925d-105">FindPrivateKey ist ein Beispiel, das vor der Verwendung kompiliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="f925d-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="f925d-106">Anweisungen zum Erstellen des Tools FindPrivateKey finden Sie im Abschnitt so [Erstellen Sie das FindPrivateKey-Projekt](#to-build-the-findprivatekey-project) .</span><span class="sxs-lookup"><span data-stu-id="f925d-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="f925d-107">X.509-Zertifikate werden von einem Administrator oder einem beliebigen Benutzer auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f925d-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="f925d-108">Auf das Zertifikat kann jedoch von einem Dienst zugegriffen werden, der unter einem anderen Konto ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f925d-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="f925d-109">Beispielsweise das Netzwerkdienst Konto.</span><span class="sxs-lookup"><span data-stu-id="f925d-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="f925d-110">Dieses Konto verfügt möglicherweise nicht über Zugriff auf die Privatschlüsseldatei, da das Zertifikat nicht ursprünglich von diesem Konto installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f925d-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="f925d-111">Das Tool FindPrivateKey gibt den Speicherort der Privatschlüsseldatei eines X.509-Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="f925d-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="f925d-112">Sie können Berechtigungen in dieser Datei hinzufügen oder entfernen, wenn Sie den Speicherort der Privatschlüsseldatei der jeweiligen X.509-Zertifikate kennen.</span><span class="sxs-lookup"><span data-stu-id="f925d-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="f925d-113">In den Beispielen für die Verwendung von Zertifikaten für die Sicherheit wird das Tool FindPrivateKey in der Datei *Setup. bat* verwendet.</span><span class="sxs-lookup"><span data-stu-id="f925d-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="f925d-114">Nachdem die Datei mit dem privaten Schlüssel gefunden wurde, können Sie andere Tools, wie z. b *. cacls. exe* , verwenden, um die entsprechenden Zugriffsrechte auf die Datei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f925d-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="f925d-115">Wenn Sie einen Windows Communication Foundation (WCF)-Dienst unter einem Benutzerkonto ausführen (z. b. eine selbstgeh ostete ausführbare Datei), stellen Sie sicher, dass das Benutzerkonto schreibgeschützten Zugriff auf die Datei hat.</span><span class="sxs-lookup"><span data-stu-id="f925d-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="f925d-116">Beim Ausführen eines WCF-Dienstanbieter unter Internetinformationsdienste (IIS) werden die Standardkonten, unter denen der-Dienst ausgeführt wird, der Netzwerkdienst in IIS 7 und früheren Versionen oder die Anwendungs Pool Identität auf IIS 7,5 und höheren Versionen.</span><span class="sxs-lookup"><span data-stu-id="f925d-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="f925d-117">Weitere Informationen finden Sie unter [Anwendungs Pool Identitäten](/iis/manage/configuring-security/application-pool-identities).</span><span class="sxs-lookup"><span data-stu-id="f925d-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="f925d-118">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f925d-118">Examples</span></span>

<span data-ttu-id="f925d-119">Wenn Sie auf ein Zertifikat zugreifen, für das der Prozess nicht über Leseberechtigungen verfügt, wird eine Ausnahme Meldung wie im folgenden Beispiel angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f925d-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="f925d-120">Verwenden Sie in diesem Fall das Tool FindPrivateKey, um die Datei mit dem privaten Schlüssel zu suchen, und legen Sie dann das Zugriffsrecht für den Prozess fest, unter dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f925d-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="f925d-121">Dies kann z. b. mit dem Tool cacls. exe erfolgen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f925d-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="f925d-122">So erstellen Sie das FindPrivateKey-Projekt</span><span class="sxs-lookup"><span data-stu-id="f925d-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="f925d-123">Um das Projekt herunterzuladen, besuchen Sie [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span><span class="sxs-lookup"><span data-stu-id="f925d-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="f925d-124">Öffnen Sie den Datei-Explorer, und navigieren Sie zum Ordner *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* unter dem Verzeichnis, in dem Sie das Beispiel installiert haben.</span><span class="sxs-lookup"><span data-stu-id="f925d-124">Open File Explorer and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="f925d-125">Doppelklicken Sie auf das Symbol für die SLN-Datei, um diese in Visual Studio zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f925d-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="f925d-126">Wählen Sie im Menü **Erstellen** die Option Projekt Mappe **neu erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="f925d-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="f925d-127">Beim Aufbau der Lösung wird die folgende Datei generiert: FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="f925d-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="f925d-128">Konventionen – Befehlszeilen Einträge</span><span class="sxs-lookup"><span data-stu-id="f925d-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="f925d-129">"[*Option*]" stellt einen optionalen Satz von Parametern dar.</span><span class="sxs-lookup"><span data-stu-id="f925d-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="f925d-130">"{*Option*}" stellt einen obligatorischen Satz von Parametern dar.</span><span class="sxs-lookup"><span data-stu-id="f925d-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="f925d-131">"*Option1* &#124; *Option2*" stellt eine Auswahl zwischen Options Sätzen dar.</span><span class="sxs-lookup"><span data-stu-id="f925d-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="f925d-132">"\<*value*>" stellt einen Parameterwert dar, der eingegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="f925d-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="f925d-133">Verwendung</span><span class="sxs-lookup"><span data-stu-id="f925d-133">Usage</span></span>

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="f925d-134">Erläuterungen:</span><span class="sxs-lookup"><span data-stu-id="f925d-134">Where:</span></span>

| <span data-ttu-id="f925d-135">Parameter</span><span class="sxs-lookup"><span data-stu-id="f925d-135">Parameter</span></span>         | <span data-ttu-id="f925d-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f925d-136">Description</span></span>                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | <span data-ttu-id="f925d-137">Der Antragsteller Name des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="f925d-137">The subject name of the certificate</span></span>                                               |
| `<thumbprint>`  | <span data-ttu-id="f925d-138">Der Fingerabdruck des Zertifikats (Sie können das Tool "Certmgr. exe" verwenden, um dies zu finden)</span><span class="sxs-lookup"><span data-stu-id="f925d-138">The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)</span></span> |
| `-f`            | <span data-ttu-id="f925d-139">nur Ausgabe Dateiname</span><span class="sxs-lookup"><span data-stu-id="f925d-139">output file name only</span></span>                                                             |
| `-d`            | <span data-ttu-id="f925d-140">nur Ausgabeverzeichnis</span><span class="sxs-lookup"><span data-stu-id="f925d-140">output directory only</span></span>                                                             |
| `-a`            | <span data-ttu-id="f925d-141">absoluten Dateinamen ausgeben</span><span class="sxs-lookup"><span data-stu-id="f925d-141">output absolute file name</span></span>                                                         |

<span data-ttu-id="f925d-142">Wenn keine Parameter an der Eingabeaufforderung angegeben werden, wird der Hilfetext mit diesen Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f925d-142">If no parameters are specified at the command prompt, then help text with this information is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="f925d-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f925d-143">Examples</span></span>

<span data-ttu-id="f925d-144">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragsteller Namen "CN = localhost" im persönlichen Speicher des aktuellen Benutzers ermittelt.</span><span class="sxs-lookup"><span data-stu-id="f925d-144">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="f925d-145">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Antragsteller Namen "CN = localhost" im persönlichen Speicher des aktuellen Benutzers gesucht und der vollständige Verzeichnispfad ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="f925d-145">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="f925d-146">In diesem Beispiel wird der Dateiname des Zertifikats mit dem Fingerabdruck "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" im persönlichen Speicher des lokalen Computers gesucht.</span><span class="sxs-lookup"><span data-stu-id="f925d-146">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
