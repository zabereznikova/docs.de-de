---
title: Certmgr.exe (Certificate Manager-Tool)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
caps.latest.revision: 27
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bd5d1011a8f8aeadfc7729c3a4f6f56a033110a9
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="certmgrexe-certificate-manager-tool"></a><span data-ttu-id="abab5-102">Certmgr.exe (Certificate Manager-Tool)</span><span class="sxs-lookup"><span data-stu-id="abab5-102">Certmgr.exe (Certificate Manager Tool)</span></span>
<span data-ttu-id="abab5-103">Mit dem Certificate Manager-Tool (Certmgr.exe) können Sie Zertifikate, Zertifikatvertrauenslisten (Certificate Trust Lists, CTLs) und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) verwalten.</span><span class="sxs-lookup"><span data-stu-id="abab5-103">The Certificate Manager tool (Certmgr.exe) manages certificates, certificate trust lists (CTLs), and certificate revocation lists (CRLs).</span></span>  
  
 <span data-ttu-id="abab5-104">Das Certificate Manager-Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="abab5-104">The Certificate Manager is automatically installed with Visual Studio.</span></span> <span data-ttu-id="abab5-105">Verwenden Sie zum Starten des Tools die [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="abab5-105">To start the tool, use the [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="abab5-106">Das Certificate Manager-Tool (Certmgr.exe) ist ein Befehlszeilendienstprogramm, wohingegen "Zertifikate" (Certmgr.msc) ein MMC-Snap-In (Microsoft Management Console) ist.</span><span class="sxs-lookup"><span data-stu-id="abab5-106">The Certificate Manager tool (Certmgr.exe) is a command-line utility, whereas Certificates (Certmgr.msc) is a Microsoft Management Console (MMC) snap-in.</span></span> <span data-ttu-id="abab5-107">Da sich „Certmgr.msc“ normalerweise im Windows-Systemverzeichnis befindet, kann durch die Eingabe von `certmgr` in der Befehlszeile das MMC-Snap-In „Zertifikate“ geladen werden, auch wenn Sie die Visual Studio-Eingabeaufforderung geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="abab5-107">Because Certmgr.msc is usually found in the Windows System directory, entering `certmgr` at the command line may load the Certificates MMC snap-in even if you have opened the Visual Studio Command Prompt.</span></span> <span data-ttu-id="abab5-108">Dies geschieht, weil der Pfad zum Snap-In dem Pfad für das Certificate Manager-Tool in der PATH-Umgebungsvariablen vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="abab5-108">This occurs because the path to the snap-in precedes the path to the Certificate Manager tool in the PATH environment variable.</span></span> <span data-ttu-id="abab5-109">Wenn dieses Problem auftritt, können Sie "Certmgr.exe"-Befehle ausführen, indem Sie den Pfad zu der ausführbaren Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="abab5-109">If you encounter this problem, you can execute Certmgr.exe commands by specifying the path to the executable.</span></span>  
  
 <span data-ttu-id="abab5-110">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="abab5-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="abab5-111">Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="abab5-111">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="abab5-112">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="abab5-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="abab5-113">Einen Überblick über X.509-Zertifikate finden Sie unter [Arbeiten mit Zertifikaten](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="abab5-113">For an overview of X.509 certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
 <span data-ttu-id="abab5-114">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="abab5-114">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abab5-115">Syntax</span><span class="sxs-lookup"><span data-stu-id="abab5-115">Syntax</span></span>  
  
```  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abab5-116">Parameter</span><span class="sxs-lookup"><span data-stu-id="abab5-116">Parameters</span></span>  
  
|<span data-ttu-id="abab5-117">Argument</span><span class="sxs-lookup"><span data-stu-id="abab5-117">Argument</span></span>|<span data-ttu-id="abab5-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abab5-118">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="abab5-119">*sourceStorename*</span><span class="sxs-lookup"><span data-stu-id="abab5-119">*sourceStorename*</span></span>|<span data-ttu-id="abab5-120">Der Zertifikatspeicher, der die vorhandenen Zertifikate, die CTLs oder CRLs enthält, die hinzugefügt, gelöscht, gespeichert oder angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="abab5-120">The certificate store that contains the existing certificates, CTLs, or CRLs to add, delete, save, or display.</span></span> <span data-ttu-id="abab5-121">Dabei kann es sich um eine Speicherdatei oder einen Systemspeicher handeln.</span><span class="sxs-lookup"><span data-stu-id="abab5-121">This can be a store file or a systems store.</span></span>|  
|<span data-ttu-id="abab5-122">*destinationStorename*</span><span class="sxs-lookup"><span data-stu-id="abab5-122">*destinationStorename*</span></span>|<span data-ttu-id="abab5-123">Der Ausgabezertifikatsspeicher bzw. die Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="abab5-123">The output certificate store or file.</span></span>|  
  
|<span data-ttu-id="abab5-124">Option</span><span class="sxs-lookup"><span data-stu-id="abab5-124">Option</span></span>|<span data-ttu-id="abab5-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="abab5-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="abab5-126">**/add**</span><span class="sxs-lookup"><span data-stu-id="abab5-126">**/add**</span></span>|<span data-ttu-id="abab5-127">Fügt einem Zertifikatsspeicher Zertifikate, CTLs und CRLs hinzu.</span><span class="sxs-lookup"><span data-stu-id="abab5-127">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>|  
|<span data-ttu-id="abab5-128">**/all**</span><span class="sxs-lookup"><span data-stu-id="abab5-128">**/all**</span></span>|<span data-ttu-id="abab5-129">Fügt bei der Verwendung mit **/add** alle Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="abab5-129">Adds all entries when used with **/add**.</span></span> <span data-ttu-id="abab5-130">Löscht bei der Verwendung mit **/del** alle Einträge.</span><span class="sxs-lookup"><span data-stu-id="abab5-130">Deletes all entries when used with **/del**.</span></span> <span data-ttu-id="abab5-131">Zeigt bei der Verwendung ohne die Option **/add** oder **/del** alle Einträge an.</span><span class="sxs-lookup"><span data-stu-id="abab5-131">Displays all entries when used without the **/add** or **/del** options.</span></span> <span data-ttu-id="abab5-132">Die Option **/all** kann nicht mit **/put** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="abab5-132">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="abab5-133">**/c**</span><span class="sxs-lookup"><span data-stu-id="abab5-133">**/c**</span></span>|<span data-ttu-id="abab5-134">Fügt bei der Verwendung mit **/add** Zertifikate hinzu.</span><span class="sxs-lookup"><span data-stu-id="abab5-134">Adds certificates when used with **/add**.</span></span> <span data-ttu-id="abab5-135">Löscht Zertifikate bei der Verwendung mit **/del**.</span><span class="sxs-lookup"><span data-stu-id="abab5-135">Deletes certificates when used with **/del**.</span></span> <span data-ttu-id="abab5-136">Speichert Zertifikate bei der Verwendung mit **/put**.</span><span class="sxs-lookup"><span data-stu-id="abab5-136">Saves certificates when used with **/put**.</span></span> <span data-ttu-id="abab5-137">Zeigt bei der Verwendung ohne die Optionen **/add**, **/del** und **/put** Zertifikate an.</span><span class="sxs-lookup"><span data-stu-id="abab5-137">Displays certificates when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="abab5-138">**/CRL**</span><span class="sxs-lookup"><span data-stu-id="abab5-138">**/CRL**</span></span>|<span data-ttu-id="abab5-139">Fügt bei der Verwendung mit **/add** CRLs hinzu.</span><span class="sxs-lookup"><span data-stu-id="abab5-139">Adds CRLs when used with **/add**.</span></span> <span data-ttu-id="abab5-140">Löscht CRLs bei der Verwendung mit**/del**.</span><span class="sxs-lookup"><span data-stu-id="abab5-140">Deletes CRLs when used with **/del**.</span></span> <span data-ttu-id="abab5-141">Speichert CRLs bei der Verwendung mit **/put**.</span><span class="sxs-lookup"><span data-stu-id="abab5-141">Saves CRLs when used with **/put**.</span></span> <span data-ttu-id="abab5-142">Zeigt bei der Verwendung ohne die Optionen **/add**, **/del** und **/put** CRLs an.</span><span class="sxs-lookup"><span data-stu-id="abab5-142">Displays CRLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="abab5-143">**/CTL**</span><span class="sxs-lookup"><span data-stu-id="abab5-143">**/CTL**</span></span>|<span data-ttu-id="abab5-144">Fügt bei der Verwendung mit **/add** CTLs hinzu.</span><span class="sxs-lookup"><span data-stu-id="abab5-144">Adds CTLs when used with **/add**.</span></span> <span data-ttu-id="abab5-145">Löscht CTLs bei der Verwendung mit **/del**.</span><span class="sxs-lookup"><span data-stu-id="abab5-145">Deletes CTLs when used with **/del**.</span></span> <span data-ttu-id="abab5-146">Speichert CTLs bei der Verwendung mit **/put**.</span><span class="sxs-lookup"><span data-stu-id="abab5-146">Saves CTLs when used with **/put**.</span></span> <span data-ttu-id="abab5-147">Zeigt bei der Verwendung ohne die Option **/add**, **/del** oder **/put** CTLs an.</span><span class="sxs-lookup"><span data-stu-id="abab5-147">Displays CTLs when used without the **/add**, **/del**, or **/put** option.</span></span>|  
|<span data-ttu-id="abab5-148">**/del**</span><span class="sxs-lookup"><span data-stu-id="abab5-148">**/del**</span></span>|<span data-ttu-id="abab5-149">Löscht Zertifikate, CTLs und CRLs aus einem Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="abab5-149">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>|  
|<span data-ttu-id="abab5-150">**/e** *encodingType*</span><span class="sxs-lookup"><span data-stu-id="abab5-150">**/e** *encodingType*</span></span>|<span data-ttu-id="abab5-151">Gibt den Codierungstyp des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="abab5-151">Specifies the certificate encoding type.</span></span> <span data-ttu-id="abab5-152">Die Standardeinstellung ist `X509_ASN_ENCODING`.</span><span class="sxs-lookup"><span data-stu-id="abab5-152">The default is `X509_ASN_ENCODING`.</span></span>|  
|<span data-ttu-id="abab5-153">**/f** *dwFlags*</span><span class="sxs-lookup"><span data-stu-id="abab5-153">**/f** *dwFlags*</span></span>|<span data-ttu-id="abab5-154">Gibt das Flag zum Öffnen des Speichers an.</span><span class="sxs-lookup"><span data-stu-id="abab5-154">Specifies the store open flag.</span></span> <span data-ttu-id="abab5-155">Dies ist der an *CertOpenStore* übergebene Parameter **dwFlags**.</span><span class="sxs-lookup"><span data-stu-id="abab5-155">This is the *dwFlags* parameter passed to **CertOpenStore**.</span></span> <span data-ttu-id="abab5-156">Der Standardwert ist CERT_SYSTEM_STORE_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="abab5-156">The default value is CERT_SYSTEM_STORE_CURRENT_USER.</span></span> <span data-ttu-id="abab5-157">Diese Option wird nur bei der Verwendung der Option **/y** berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="abab5-157">This option is considered only if the **/y** option is used.</span></span>|  
|<span data-ttu-id="abab5-158">**/h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="abab5-158">**/h**[**elp**]</span></span>|<span data-ttu-id="abab5-159">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="abab5-159">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="abab5-160">**/n** *name*</span><span class="sxs-lookup"><span data-stu-id="abab5-160">**/n** *nam*</span></span>|<span data-ttu-id="abab5-161">Gibt den allgemeinen Namen des Zertifikats an, das hinzugefügt, gelöscht oder gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="abab5-161">Specifies the common name of the certificate to add, delete, or save.</span></span> <span data-ttu-id="abab5-162">Diese Option kann nur für Zertifikate und nicht für CTLs und CRLs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="abab5-162">This option can only be used with certificates; it cannot be used with CTLs or CRLs.</span></span>|  
|<span data-ttu-id="abab5-163">**/put**</span><span class="sxs-lookup"><span data-stu-id="abab5-163">**/put**</span></span>|<span data-ttu-id="abab5-164">Speichert ein X.509-Zertifikat, eine CTL oder eine CRL aus einem Zertifikatspeicher in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="abab5-164">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span> <span data-ttu-id="abab5-165">Die Datei wird im Format X.509 gespeichert.</span><span class="sxs-lookup"><span data-stu-id="abab5-165">The file is saved in X.509 format.</span></span> <span data-ttu-id="abab5-166">Sie können die Option **/7** zusammen mit der Option **/put** verwenden, um die Datei im PKCS #7-Format zu speichern.</span><span class="sxs-lookup"><span data-stu-id="abab5-166">You can use the **/7** option with the **/put** option to save the file in PKCS #7 format.</span></span> <span data-ttu-id="abab5-167">Auf die Option **/put** muss entweder **/c**, **/CTL** oder **/CR** folgen.</span><span class="sxs-lookup"><span data-stu-id="abab5-167">The **/put** option must be followed by either **/c**, **/CTL**, or **/CRL**.</span></span> <span data-ttu-id="abab5-168">Die Option **/all** kann nicht mit **/put** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="abab5-168">The **/all** option cannot be used with **/put**.</span></span>|  
|<span data-ttu-id="abab5-169">**/r** *location*</span><span class="sxs-lookup"><span data-stu-id="abab5-169">**/r** *location*</span></span>|<span data-ttu-id="abab5-170">Gibt den Speicherort des Systemspeichers in der Registrierung an.</span><span class="sxs-lookup"><span data-stu-id="abab5-170">Identifies the registry location of the system store.</span></span> <span data-ttu-id="abab5-171">Diese Option wird nur berücksichtigt, wenn Sie die Option **/s** angeben.</span><span class="sxs-lookup"><span data-stu-id="abab5-171">This option is considered only if you specify the **/s** option.</span></span> <span data-ttu-id="abab5-172">Für *location* muss einer der folgenden Werte angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="abab5-172">*location* must be one of the following:</span></span><br /><br /> <span data-ttu-id="abab5-173">-   `currentUser` gibt an, dass sich der Zertifikatspeicher unter dem Schlüssel HKEY_CURRENT_USER befindet.</span><span class="sxs-lookup"><span data-stu-id="abab5-173">-   `currentUser` indicates that the certificate store is under the HKEY_CURRENT_USER key.</span></span> <span data-ttu-id="abab5-174">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="abab5-174">This is the default.</span></span><br /><span data-ttu-id="abab5-175">-   `localMachine` gibt an, dass sich der Zertifikatspeicher unter dem Schlüssel HKEY_LOCAL_MACHINE befindet.</span><span class="sxs-lookup"><span data-stu-id="abab5-175">-   `localMachine` indicates that the certificate store is under the HKEY_LOCAL_MACHINE key.</span></span>|  
|<span data-ttu-id="abab5-176">**/s**</span><span class="sxs-lookup"><span data-stu-id="abab5-176">**/s**</span></span>|<span data-ttu-id="abab5-177">Gibt an, dass der Zertifikatspeicher ein Systemspeicher ist.</span><span class="sxs-lookup"><span data-stu-id="abab5-177">Indicates that the certificate store is a system store.</span></span> <span data-ttu-id="abab5-178">Wenn Sie diese Option nicht angeben, wird angenommen, dass der Speicher vom Typ **StoreFile** ist.</span><span class="sxs-lookup"><span data-stu-id="abab5-178">If you do not specify this option, the store is considered to be a **StoreFile**.</span></span>|  
|<span data-ttu-id="abab5-179">**/sha1** *sha1Hash*</span><span class="sxs-lookup"><span data-stu-id="abab5-179">**/sha1** *sha1Hash*</span></span>|<span data-ttu-id="abab5-180">Gibt den SHA1-Hash des Zertifikats, der CTL oder der CRL an, das bzw. die hinzugefügt, gelöscht oder gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="abab5-180">Specifies the SHA1 hash of the certificate, CTL, or CRL to add, delete, or save.</span></span>|  
|<span data-ttu-id="abab5-181">**/v**</span><span class="sxs-lookup"><span data-stu-id="abab5-181">**/v**</span></span>|<span data-ttu-id="abab5-182">Gibt den ausführlichen Modus an und zeigt detaillierte Informationen über Zertifikate, CTLs und CRLs an.</span><span class="sxs-lookup"><span data-stu-id="abab5-182">Specifies verbose mode; displays detailed information about certificates, CTLs, and CRLs.</span></span> <span data-ttu-id="abab5-183">Diese Option kann nicht mit den Optionen **/add**, **/del** und **/put** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="abab5-183">This option cannot be used with the **/add**, **/del**, or **/put** options.</span></span>|  
|<span data-ttu-id="abab5-184">**/y** *provider*</span><span class="sxs-lookup"><span data-stu-id="abab5-184">**/y** *provider*</span></span>|<span data-ttu-id="abab5-185">Gibt den Namen des Speicheranbieters an.</span><span class="sxs-lookup"><span data-stu-id="abab5-185">Specifies the store provider name.</span></span>|  
|<span data-ttu-id="abab5-186">**/7**</span><span class="sxs-lookup"><span data-stu-id="abab5-186">**/7**</span></span>|<span data-ttu-id="abab5-187">Speichert den Zielspeicher als PKCS #7-Objekt.</span><span class="sxs-lookup"><span data-stu-id="abab5-187">Saves the destination store as a PKCS #7 object.</span></span>|  
|<span data-ttu-id="abab5-188">**/?**</span><span class="sxs-lookup"><span data-stu-id="abab5-188">**/?**</span></span>|<span data-ttu-id="abab5-189">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="abab5-189">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="abab5-190">Hinweise</span><span class="sxs-lookup"><span data-stu-id="abab5-190">Remarks</span></span>  
 <span data-ttu-id="abab5-191">Von "Certmgr.exe" werden die folgenden Basisfunktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="abab5-191">Certmgr.exe performs the following basic functions:</span></span>  
  
-   <span data-ttu-id="abab5-192">Zeigt Zertifikate, CTLs und CRLs in der Konsole an.</span><span class="sxs-lookup"><span data-stu-id="abab5-192">Displays certificates, CTLs, and CRLs to the console.</span></span>  
  
-   <span data-ttu-id="abab5-193">Fügt einem Zertifikatsspeicher Zertifikate, CTLs und CRLs hinzu.</span><span class="sxs-lookup"><span data-stu-id="abab5-193">Adds certificates, CTLs, and CRLs to a certificate store.</span></span>  
  
-   <span data-ttu-id="abab5-194">Löscht Zertifikate, CTLs und CRLs aus einem Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="abab5-194">Deletes certificates, CTLs, and CRLs from a certificate store.</span></span>  
  
-   <span data-ttu-id="abab5-195">Speichert ein X.509-Zertifikat, eine CTL oder eine CRL aus einem Zertifikatspeicher in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="abab5-195">Saves an X.509 certificate, CTL, or CRL from a certificate store to a file.</span></span>  
  
 <span data-ttu-id="abab5-196">In „Certmgr.exe“ werden zwei Typen von Zertifikatspeichern verwendet: **StoreFile** und Systemspeicher.</span><span class="sxs-lookup"><span data-stu-id="abab5-196">Certmgr.exe works with two types of certificate stores: **StoreFile** and system store.</span></span> <span data-ttu-id="abab5-197">Sie müssen den Typ des Zertifikatspeichers nicht angeben. "Certmgr.exe" kann den Speichertyp erkennen und die entsprechenden Operationen ausführen.</span><span class="sxs-lookup"><span data-stu-id="abab5-197">It is not necessary to specify the type of certificate store; Certmgr.exe can identify the store type and perform the appropriate operations.</span></span>  
  
 <span data-ttu-id="abab5-198">Wird "Certmgr.exe" ohne Angabe von Optionen ausgeführt, wird das Snap-In "Certmgr.msc" gestartet. Dessen grafische Benutzeroberfläche (GUI) erleichtert die Aufgaben der Zertifikatsverwaltung, die auch über die Befehlszeile zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="abab5-198">Running Certmgr.exe without specifying any options launches the certmgr.msc snap-in, which has a GUI that helps with the certificate management tasks that are also available from the command line.</span></span> <span data-ttu-id="abab5-199">Die grafische Benutzeroberfläche bietet einen Import-Assistenten, der Zertifikate, CTLs und CRLs vom Datenträger in einen Zertifikatspeicher kopiert.</span><span class="sxs-lookup"><span data-stu-id="abab5-199">The GUI provides an import wizard, which copies certificates, CTLs, and CRLs from your disk to a certificate store.</span></span>  
  
 <span data-ttu-id="abab5-200">Sie können die Namen von "X509Certificate"-Speichern für die Parameter `sourceStorename` und `destinationStorename` suchen, indem Sie den folgenden Code kompilieren und ausführen.</span><span class="sxs-lookup"><span data-stu-id="abab5-200">You can find the names of X509Certificate stores for the `sourceStorename` and `destinationStorename` parameters by compiling and running the following code.</span></span>  
  
 <span data-ttu-id="abab5-201">[!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)] [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="abab5-201">[!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)] [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]</span></span>  
  
 <span data-ttu-id="abab5-202">Weitere Informationen zu Zertifikaten finden Sie unter [Arbeiten mit Zertifikaten](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="abab5-202">For more information about certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="abab5-203">Beispiele</span><span class="sxs-lookup"><span data-stu-id="abab5-203">Examples</span></span>  
 <span data-ttu-id="abab5-204">Mit dem folgenden Befehl wird der Standardsystemspeicher `my` mit ausführlicher Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="abab5-204">The following command displays a default system store called `my` with verbose output.</span></span>  
  
```  
certmgr /v /s my  
```  
  
 <span data-ttu-id="abab5-205">Mit dem folgenden Befehl werden alle Zertifikate in der Datei `myFile.ext` einer neuen Datei mit dem Namen `newFile.ext` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="abab5-205">The following command adds all the certificates in a file called `myFile.ext` to a new file called `newFile.ext`.</span></span>  
  
```  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 <span data-ttu-id="abab5-206">Mit dem folgenden Befehl wird das Zertifikat in der Datei `testcert.cer` zum Systemspeicher `my` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="abab5-206">The following command adds the certificate in a file named `testcert.cer` to the `my` system store.</span></span>  
  
```  
certmgr /add /c testcert.cer /s my  
```  
  
 <span data-ttu-id="abab5-207">Mit dem folgenden Befehl wird das Zertifikat in der Datei `TrustedCert.cer` zum Stammzertifikatsspeicher hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="abab5-207">The following command adds the certificate in a file named `TrustedCert.cer` to the root certificate store.</span></span>  
  
```  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 <span data-ttu-id="abab5-208">Mit dem folgenden Befehl wird ein Zertifikat mit dem allgemeinen Namen `myCert` im Systemspeicher `my` in die Datei `newCert.cer` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="abab5-208">The following command saves a certificate with the common name `myCert` in the `my` system store to a file called `newCert.cer`.</span></span>  
  
```  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 <span data-ttu-id="abab5-209">Mit dem folgenden Befehl werden alle CTLs im Systemspeicher `my` gelöscht. Der sich ergebende Speicher wird anschließend in der Datei `newStore.str` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="abab5-209">The following command deletes all CTLs in the `my` system store and saves the resulting store to a file called `newStore.str`.</span></span>  
  
```  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 <span data-ttu-id="abab5-210">Mit dem folgenden Befehl wird ein Zertifikat im Systemspeicher `my` in der Datei `newFile` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="abab5-210">The following command saves a certificate in the `my` system store in the file `newFile`.</span></span> <span data-ttu-id="abab5-211">Sie werden aufgefordert, die Nummer des Zertifikats aus `my` einzugeben, das in `newFile` abgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="abab5-211">You will be prompted to enter the certificate number from `my` to put in `newFile`.</span></span>  
  
```  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a><span data-ttu-id="abab5-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abab5-212">See Also</span></span>  
 <span data-ttu-id="abab5-213">[Tools](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="abab5-213">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 <span data-ttu-id="abab5-214">[Makecert.exe (Certificate Creation-Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span><span class="sxs-lookup"><span data-stu-id="abab5-214">[Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span></span>  
 [<span data-ttu-id="abab5-215">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="abab5-215">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

