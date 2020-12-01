---
title: Certmgr.exe (Certificate Manager-Tool)
description: Untersuchen von Certmgr.exe, dem Certificate Manager-Tool. Dieses Tool verwaltet Zertifikate, CTLs (Certificate Trust Lists, Zertifikatsvertrauenslisten) und CRLs (Certificate Revocation Lists, Zertifikatssperrlisten).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
ms.openlocfilehash: 30a35ded6fc86af6dc6dd4bf19cdf60f66570e0c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247251"
---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="8c9c7-104">Certmgr.exe (Certificate Manager-Tool)</span><span class="sxs-lookup"><span data-stu-id="8c9c7-104">Certmgr.exe (Certificate Manager Tool)</span></span>

<span data-ttu-id="8c9c7-105">Mit dem Certificate Manager-Tool (Certmgr.exe) können Sie Zertifikate, Zertifikatvertrauenslisten (Certificate Trust Lists, CTLs) und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) verwalten.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-105">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="8c9c7-106">Das Certificate Manager-Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-106">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="8c9c7-107">Verwenden Sie zum Starten des Tools die [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="8c9c7-107">To start the tool, use the [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c9c7-108">Das Certificate Manager-Tool (Certmgr.exe) ist ein Befehlszeilendienstprogramm, wohingegen "Zertifikate" (Certmgr.msc) ein MMC-Snap-In (Microsoft Management Console) ist.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-108">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="8c9c7-109">Da sich „Certmgr.msc“ normalerweise im Windows-Systemverzeichnis befindet, kann durch die Eingabe von `certmgr` in der Befehlszeile das MMC-Snap-In „Zertifikate“ geladen werden, auch wenn Sie die Developer-Eingabeaufforderung für Visual Studio geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-109">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="8c9c7-110">Dies geschieht, weil der Pfad zum Snap-In dem Pfad für das Certificate Manager-Tool in der PATH-Umgebungsvariablen vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-110">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="8c9c7-111">Wenn dieses Problem auftritt, können Sie "Certmgr.exe"-Befehle ausführen, indem Sie den Pfad zu der ausführbaren Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-111">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="8c9c7-112">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-112">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="8c9c7-113">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-113">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="8c9c7-114">Weitere Informationen finden Sie unter [Eingabeaufforderungen](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="8c9c7-114">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="8c9c7-115">Einen Überblick über X.509-Zertifikate finden Sie unter [Arbeiten mit Zertifikaten](../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="8c9c7-115">For an overview of X.509 certificates, see [Working with Certificates](../wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="8c9c7-116">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8c9c7-116">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c9c7-117">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c9c7-117">Syntax</span></span>  
  
```console  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c9c7-118">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c9c7-118">Parameters</span></span>  
  
|<span data-ttu-id="8c9c7-119">Argument</span><span class="sxs-lookup"><span data-stu-id="8c9c7-119">Argument</span></span>|<span data-ttu-id="8c9c7-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c9c7-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8c9c7-121">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="8c9c7-121">*sourceStorename*</span></span>|<span data-ttu-id="8c9c7-122">Der Zertifikatspeicher, der die vorhandenen Zertifikate, die CTLs oder CRLs enthält, die hinzugefügt, gelöscht, gespeichert oder angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-122">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="8c9c7-123">Dabei kann es sich um eine Speicherdatei oder einen Systemspeicher handeln.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-123">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="8c9c7-124">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="8c9c7-124">*destinationStorename*</span></span>|<span data-ttu-id="8c9c7-125">Der Ausgabezertifikatsspeicher bzw. die Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-125">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="8c9c7-126">Option</span><span class="sxs-lookup"><span data-stu-id="8c9c7-126">Option</span></span>|<span data-ttu-id="8c9c7-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c9c7-127">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="8c9c7-128">**/add**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-128">**/add**</span></span>|<span data-ttu-id="8c9c7-129">Fügt einem Zertifikatsspeicher Zertifikate, CTLs und CRLs hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-129">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="8c9c7-130">**/all**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-130">**/all**</span></span>|<span data-ttu-id="8c9c7-131">Fügt bei der Verwendung mit **/add** alle Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-131">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="8c9c7-132">Löscht bei der Verwendung mit **/del** alle Einträge. Zeigt bei der Verwendung ohne die Option **/add** oder **/del** alle Einträge an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-132">Deletes all entries when used with **/del**. Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="8c9c7-133">Die Option **/all** kann nicht mit **/put** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-133">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="8c9c7-134">**/c**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-134">**/c**</span></span>|<span data-ttu-id="8c9c7-135">Fügt bei der Verwendung mit **/add** Zertifikate hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-135">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="8c9c7-136">Löscht Zertifikate bei der Verwendung mit **/del**. Speichert Zertifikate bei der Verwendung mit **/put**.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-136">Deletes certificates when used with **/del**. Saves certificates when used with **/put**.</span></span> <span data-ttu-id="8c9c7-137">Zeigt bei der Verwendung ohne die Optionen **/add**, **/del** und **/put** Zertifikate an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-137">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="8c9c7-138">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-138">**/CRL**</span></span>|<span data-ttu-id="8c9c7-139">Fügt bei der Verwendung mit **/add** CRLs hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-139">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="8c9c7-140">Löscht CRLs bei der Verwendung mit **/del**. Speichert CRLs bei der Verwendung mit **/put**.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-140">Deletes CRLs when used with **/del**. Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="8c9c7-141">Zeigt bei der Verwendung ohne die Optionen **/add**, **/del** und **/put** CRLs an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-141">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="8c9c7-142">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-142">**/CTL**</span></span>|<span data-ttu-id="8c9c7-143">Fügt bei der Verwendung mit **/add** CTLs hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-143">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="8c9c7-144">Löscht CTLs bei der Verwendung mit **/del**. Speichert CTLs bei der Verwendung mit **/put**.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-144">Deletes CTLs when used with **/del**. Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="8c9c7-145">Zeigt bei der Verwendung ohne die Option **/add**, **/del** oder **/put** CTLs an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-145">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="8c9c7-146">**/del**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-146">**/del**</span></span>|<span data-ttu-id="8c9c7-147">Löscht Zertifikate, CTLs und CRLs aus einem Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-147">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="8c9c7-148">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="8c9c7-148">**/e** *encodingType*</span></span>|<span data-ttu-id="8c9c7-149">Gibt den Codierungstyp des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-149">Specifies the certificate encoding type.</span></span> <span data-ttu-id="8c9c7-150">Der Standardwert ist `X509_ASN_ENCODING`.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-150">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="8c9c7-151">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="8c9c7-151">**/f** *dwFlags*</span></span>|<span data-ttu-id="8c9c7-152">Gibt das Flag zum Öffnen des Speichers an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-152">Specifies the store open flag.</span></span> <span data-ttu-id="8c9c7-153">Dies ist der an *CertOpenStore* übergebene Parameter **dwFlags**.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-153">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="8c9c7-154">Der Standardwert ist CERT_SYSTEM_STORE_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-154">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="8c9c7-155">Diese Option wird nur bei der Verwendung der Option **/y** berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-155">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="8c9c7-156">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="8c9c7-156">**/h**[**elp**]</span></span>|<span data-ttu-id="8c9c7-157">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-157">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="8c9c7-158">**/n** *nam*</span><span class="sxs-lookup"><span data-stu-id="8c9c7-158">**/n** *nam*</span></span>|<span data-ttu-id="8c9c7-159">Gibt den allgemeinen Namen des Zertifikats an, das hinzugefügt, gelöscht oder gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-159">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="8c9c7-160">Diese Option kann nur für Zertifikate und nicht für CTLs und CRLs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-160">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="8c9c7-161">**/put**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-161">**/put**</span></span>|<span data-ttu-id="8c9c7-162">Speichert ein X.509-Zertifikat, eine CTL oder eine CRL aus einem Zertifikatspeicher in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-162">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="8c9c7-163">Die Datei wird im Format X.509 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-163">The file is saved in X.509 format.</span></span> <span data-ttu-id="8c9c7-164">Sie können die Option **/7** zusammen mit der Option **/put** verwenden, um die Datei im PKCS #7-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-164">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="8c9c7-165">Auf die Option **/put** muss entweder **/c**, **/CTL** oder **/CR** folgen.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-165">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="8c9c7-166">Die Option **/all** kann nicht mit **/put** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-166">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="8c9c7-167">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="8c9c7-167">**/r** *location*</span></span>|<span data-ttu-id="8c9c7-168">Gibt den Speicherort des Systemspeichers in der Registrierung an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-168">Identifies the registry location of the system store.</span></span> <span data-ttu-id="8c9c7-169">Diese Option wird nur berücksichtigt, wenn Sie die Option **/s** angeben.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-169">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="8c9c7-170">Für *location* muss einer der folgenden Werte angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="8c9c7-170">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="8c9c7-171">-   `currentUser` gibt an, dass sich der Zertifikatspeicher unter dem Schlüssel HKEY_CURRENT_USER befindet.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-171">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="8c9c7-172">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-172">This is the default.</span></span><br /><span data-ttu-id="8c9c7-173">-   `localMachine` gibt an, dass sich der Zertifikatspeicher unter dem Schlüssel HKEY_LOCAL_MACHINE befindet.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-173">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="8c9c7-174">**/s**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-174">**/s**</span></span>|<span data-ttu-id="8c9c7-175">Gibt an, dass der Zertifikatspeicher ein Systemspeicher ist.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-175">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="8c9c7-176">Wenn Sie diese Option nicht angeben, wird angenommen, dass der Speicher vom Typ **StoreFile** ist.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-176">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="8c9c7-177">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="8c9c7-177">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="8c9c7-178">Gibt den SHA1-Hash des Zertifikats, der CTL oder der CRL an, das bzw. die hinzugefügt, gelöscht oder gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-178">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="8c9c7-179">**/v**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-179">**/v**</span></span>|<span data-ttu-id="8c9c7-180">Gibt den ausführlichen Modus an und zeigt detaillierte Informationen über Zertifikate, CTLs und CRLs an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-180">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="8c9c7-181">Diese Option kann nicht mit den Optionen **/add**, **/del** und **/put** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-181">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="8c9c7-182">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="8c9c7-182">**/y** *provider*</span></span>|<span data-ttu-id="8c9c7-183">Gibt den Namen des Speicheranbieters an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-183">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="8c9c7-184">**/7**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-184">**/7**</span></span>|<span data-ttu-id="8c9c7-185">Speichert den Zielspeicher als PKCS #7-Objekt.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-185">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="8c9c7-186">**/?**</span><span class="sxs-lookup"><span data-stu-id="8c9c7-186">**/?**</span></span>|<span data-ttu-id="8c9c7-187">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-187">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c9c7-188">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c9c7-188">Remarks</span></span>  

 <span data-ttu-id="8c9c7-189">Von "Certmgr.exe" werden die folgenden Basisfunktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="8c9c7-189">Certmgr.exe performs the following basic functions:</span></span>  
  
- <span data-ttu-id="8c9c7-190">Zeigt Zertifikate, CTLs und CRLs in der Konsole an.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-190">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
- <span data-ttu-id="8c9c7-191">Fügt einem Zertifikatsspeicher Zertifikate, CTLs und CRLs hinzu.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-191">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
- <span data-ttu-id="8c9c7-192">Löscht Zertifikate, CTLs und CRLs aus einem Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-192">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
- <span data-ttu-id="8c9c7-193">Speichert ein X.509-Zertifikat, eine CTL oder eine CRL aus einem Zertifikatspeicher in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-193">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="8c9c7-194">In „Certmgr.exe“ werden zwei Typen von Zertifikatspeichern verwendet: **StoreFile** und der Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-194">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="8c9c7-195">Sie müssen den Typ des Zertifikatspeichers nicht angeben. "Certmgr.exe" kann den Speichertyp erkennen und die entsprechenden Operationen ausführen.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-195">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="8c9c7-196">Wird "Certmgr.exe" ohne Angabe von Optionen ausgeführt, wird das Snap-In "Certmgr.msc" gestartet. Dessen grafische Benutzeroberfläche (GUI) erleichtert die Aufgaben der Zertifikatsverwaltung, die auch über die Befehlszeile zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-196">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="8c9c7-197">Die grafische Benutzeroberfläche bietet einen Import-Assistenten, der Zertifikate, CTLs und CRLs vom Datenträger in einen Zertifikatspeicher kopiert.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-197">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="8c9c7-198">Sie können die Namen von "X509Certificate"-Speichern für die Parameter `sourceStorename` und `destinationStorename` suchen, indem Sie den folgenden Code kompilieren und ausführen.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-198">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 <span data-ttu-id="8c9c7-199">Weitere Informationen zu Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](../wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="8c9c7-199">For more information about certificates, see [Working with Certificates](../wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8c9c7-200">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8c9c7-200">Examples</span></span>  

 <span data-ttu-id="8c9c7-201">Mit dem folgenden Befehl wird der Standardsystemspeicher `my` mit ausführlicher Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-201">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```console  
certmgr /v /s my  
```  
  
 <span data-ttu-id="8c9c7-202">Mit dem folgenden Befehl werden alle Zertifikate in der Datei `myFile.ext` einer neuen Datei mit dem Namen `newFile.ext` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-202">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```console  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="8c9c7-203">Mit dem folgenden Befehl wird das Zertifikat in der Datei `testcert.cer` zum Systemspeicher `my` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-203">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```console  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="8c9c7-204">Mit dem folgenden Befehl wird das Zertifikat in der Datei `TrustedCert.cer` zum Stammzertifikatsspeicher hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-204">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```console  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="8c9c7-205">Mit dem folgenden Befehl wird ein Zertifikat mit dem allgemeinen Namen `myCert` im Systemspeicher `my` in die Datei `newCert.cer` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-205">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```console  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="8c9c7-206">Mit dem folgenden Befehl werden alle CTLs im Systemspeicher `my` gelöscht. Der sich ergebende Speicher wird anschließend in der Datei `newStore.str` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-206">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```console  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="8c9c7-207">Mit dem folgenden Befehl wird ein Zertifikat im Systemspeicher `my` in der Datei `newFile` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-207">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="8c9c7-208">Sie werden aufgefordert, die Nummer des Zertifikats aus `my` einzugeben, das in `newFile` abgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c9c7-208">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```console  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c9c7-209">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c9c7-209">See also</span></span>

- [<span data-ttu-id="8c9c7-210">Extras</span><span class="sxs-lookup"><span data-stu-id="8c9c7-210">Tools</span></span>](index.md)
- [<span data-ttu-id="8c9c7-211">Makecert.exe (Tool für die Zertifikaterstellung)</span><span class="sxs-lookup"><span data-stu-id="8c9c7-211">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="8c9c7-212">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="8c9c7-212">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
