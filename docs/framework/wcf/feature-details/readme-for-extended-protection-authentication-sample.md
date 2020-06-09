---
title: Infodatei für das Beispiel zum erweiterten Schutz für die Authentifizierung
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: 9b0a3535282a1fcc1103651f5601459e80d3d8d4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601100"
---
# <a name="readme-for-extended-protection-authentication-sample"></a><span data-ttu-id="843ff-102">Infodatei für das Beispiel zum erweiterten Schutz für die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="843ff-102">ReadMe for Extended Protection Authentication Sample</span></span>

<span data-ttu-id="843ff-103">Der erweiterte Schutz ist eine Sicherheitsinitiative zum Schutz vor man-in-the-Middle-Angriffen (MITM), bei denen ein Angreifer ("man-in-the-Middle") die Anmelde Informationen eines Clients abfängt und Sie für den Zugriff auf sichere Ressourcen auf dem vorgesehenen Server des Clients verwendet.</span><span class="sxs-lookup"><span data-stu-id="843ff-103">Extended Protection is a security initiative to protect against man-in-the-middle (MITM) attacks, in which an attacker (the "man-in-the-middle") intercepts a client’s credentials and uses them to access secure resources on the client’s intended server.</span></span>

<span data-ttu-id="843ff-104">Weitere Informationen finden Sie unter [Erweiterter Schutz für die Authentifizierung Übersicht](extended-protection-for-authentication-overview.md).</span><span class="sxs-lookup"><span data-stu-id="843ff-104">For more information, see [Extended Protection for Authentication Overview](extended-protection-for-authentication-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="843ff-105">Dieses Beispiel funktioniert nur, wenn es auf IIS gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="843ff-105">This sample only works when hosted on IIS.</span></span> <span data-ttu-id="843ff-106">Es funktioniert nicht unter Visual Studio Development Server, da hier keine HTTPS-Unterstützung gegeben ist.</span><span class="sxs-lookup"><span data-stu-id="843ff-106">It does not work on Visual Studio Development Server because that does not support HTTPS.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="843ff-107">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="843ff-107">To Set Up, Build, and Run the Sample</span></span>

1. <span data-ttu-id="843ff-108">Installieren Sie IIS auf dem Computer unter "Software-> Windows-Features".</span><span class="sxs-lookup"><span data-stu-id="843ff-108">Install IIS on the machine from Add/Remove Programs -> Windows Features.</span></span>

2. <span data-ttu-id="843ff-109">Aktivieren Sie die Windows-Authentifizierung in Windows-Features: Internetinformationsdienste-> World Wide Web Services-> Sicherheit-> Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="843ff-109">Turn on Windows Authentication in Windows features: Internet Information Services -> World Wide Web Services -> Security -> Windows Authentication.</span></span>

3. <span data-ttu-id="843ff-110">Aktivieren Sie die HTTP-Aktivierung in Windows-Features: Microsoft .NET Framework 3.5.1-> Windows Communication Foundation http-Aktivierung.</span><span class="sxs-lookup"><span data-stu-id="843ff-110">Turn on HTTP Activation in Windows features: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP Activation.</span></span>

4. <span data-ttu-id="843ff-111">In diesem Beispiel muss der Client eine Verbindung über einen sicheren Kanal zum Server herstellen. Dazu muss ein Serverzertifikat vorliegen, das im IIS (Internet Information Services)-Manager installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="843ff-111">This sample requires the client to establish a secure channel with the server and so it requires the presence of a server certificate which can be installed from Internet Information Services (IIS) Manager.</span></span>

    1. <span data-ttu-id="843ff-112">Öffnen Sie die IIS-Manager-> Server Zertifikate (auf der Registerkarte Funktions Ansicht).</span><span class="sxs-lookup"><span data-stu-id="843ff-112">Open the IIS manager -> Server certificates (from the feature view tab).</span></span>

    2. <span data-ttu-id="843ff-113">Für dieses Beispiel können Sie ein selbstsigniertes Zertifikat erstellen.</span><span class="sxs-lookup"><span data-stu-id="843ff-113">For the purpose of testing this sample, you can create a self-signed certificate.</span></span> <span data-ttu-id="843ff-114">(Wenn Sie von Internet Explorer keine Meldung hinsichtlich der fehlenden Sicherheit des Zertifikats erhalten möchten, können Sie es im entsprechenden Autoritätsspeicher für vertrauenswürdige Zertifikate installieren).</span><span class="sxs-lookup"><span data-stu-id="843ff-114">(If you don’t want Internet Explorer to prompt you about the certificate not being secure, you can install it in the Trusted Certificate Root authority store).</span></span>

5. <span data-ttu-id="843ff-115">Wechseln Sie zum Aktionsbereich für die Standardwebsite.</span><span class="sxs-lookup"><span data-stu-id="843ff-115">Go to the Actions pane for the Default Web site.</span></span> <span data-ttu-id="843ff-116">Klicken Sie auf Website > Bindungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="843ff-116">Click Edit Site -> Bindings.</span></span> <span data-ttu-id="843ff-117">Falls nicht bereits vorhanden, fügen Sie HTTPS als Typ mit der Anschlussnummer 443 hinzu, und weisen Sie das im vorherigen Schritt erstellte SSL-Zertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="843ff-117">Add HTTPS as a type if it is not already present, with port number 443, and assign the SSL certificate created in the above step.</span></span>

6. <span data-ttu-id="843ff-118">Erstellen Sie den Dienst.</span><span class="sxs-lookup"><span data-stu-id="843ff-118">Build the service.</span></span> <span data-ttu-id="843ff-119">In IIS wird gemäß der in den Projekteigenschaften angegebenen Postbuildaktion ein virtuelles Verzeichnis erstellt, und die für das Webhosting des Diensts erforderlichen DLL-, SVC- und CONFIG-Dateien werden kopiert.</span><span class="sxs-lookup"><span data-stu-id="843ff-119">This creates a virtual directory in IIS for you (from the post build action specified in the project properties) and copies the dll, .svc and config files as needed for a service to be Web hosted.</span></span>

7. <span data-ttu-id="843ff-120">Öffnen Sie den IIS-Manager.</span><span class="sxs-lookup"><span data-stu-id="843ff-120">Open the IIS Manager.</span></span> <span data-ttu-id="843ff-121">Klicken Sie mit der rechten Maustaste auf das virtuelle Verzeichnis (ExtendedProtection), das Sie im vorhergehenden Schritt erstellt haben, und wählen Sie die Option zum Konvertieren in eine Anwendung.</span><span class="sxs-lookup"><span data-stu-id="843ff-121">Right-click the virtual directory (ExtendedProtection) that you created in the previous step and select Convert to Application.</span></span>

8. <span data-ttu-id="843ff-122">Öffnen Sie das Authentifizierungsmodul für das virtuelle Verzeichnis in IIS Manager, und aktivieren Sie die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="843ff-122">Open the Authentication module in IIS Manager for this virtual directory and enable Windows Authentication.</span></span>

9. <span data-ttu-id="843ff-123">Öffnen Sie die erweiterten Einstellungen für die Windows-Authentifizierung für dieses virtuelle Verzeichnis, und legen Sie es auf "Erforderlich" fest, da in diesem Beispiel die entsprechende ExtendedProtection-Einstellung auf "Immer" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="843ff-123">Open the Advanced Settings for Windows Authentication for this virtual directory and set it to Required, since, in the sample, the corresponding ExtendedProtection setting is set to Always.</span></span>

10. <span data-ttu-id="843ff-124">Testen Sie den Dienst, indem Sie von einem Browserfenster aus auf die URL zugreifen.</span><span class="sxs-lookup"><span data-stu-id="843ff-124">You can test the service by accessing the URL from a browser window.</span></span> <span data-ttu-id="843ff-125">Möchten Sie von einem Computer im Netzwerk aus auf die URL zugreifen, konfigurieren Sie die Firewall entsprechend, damit ein- und ausgehende HTTP- und HTTPS-Verbindungen hergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="843ff-125">If you want to access this URL from a cross machine, make sure that the firewall is opened for all incoming HTTP and HTTPS connections.</span></span>

11. <span data-ttu-id="843ff-126">Öffnen Sie die Client Konfigurationsdatei, und geben Sie einen vollständigen Computernamen für das \<client>  -  \<endpoint> -address-Attribut an \<full_machine_name> .</span><span class="sxs-lookup"><span data-stu-id="843ff-126">Open the client config file and provide a full machine name for the \<client> - \<endpoint> - address attribute, replacing \<full_machine_name>.</span></span>

12. <span data-ttu-id="843ff-127">Führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="843ff-127">Run the client.</span></span> <span data-ttu-id="843ff-128">Der Client kommuniziert mit dem Dienst über einen sicheren Kanal und verwendet verdeckt die erweiterte Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="843ff-128">The client communicates to the service by establishing a secure channel and using extended protection under the covers.</span></span>
