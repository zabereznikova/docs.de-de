---
title: Cert2spc.exe (Software Publisher Certificate Test-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c1d1944ae06ea26ce9bf7b4726e79155768d444
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405300"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="1bc4e-102">Cert2spc.exe (Software Publisher Certificate Test-Tool)</span><span class="sxs-lookup"><span data-stu-id="1bc4e-102">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>
<span data-ttu-id="1bc4e-103">Das Software Publisher Certificate Test-Tool erstellt ein SPC (Software Publisher's Certificate, Softwareherausgeberzertifikat) aus einem oder mehreren X.509-Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-103">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="1bc4e-104">"Cert2spc.exe" wird ausschließlich zu Textzwecken verwendet.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-104">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="1bc4e-105">Sie erhalten ein gültiges SPC von einer Zertifizierungsstelle, beispielsweise VeriSign oder Thawte.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-105">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="1bc4e-106">Weitere Informationen zum Erstellen von X.509-Zertifikaten finden Sie unter [Makecert.exe (Certificate Creation-Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d).</span><span class="sxs-lookup"><span data-stu-id="1bc4e-106">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d).</span></span>  
  
 <span data-ttu-id="1bc4e-107">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="1bc4e-108">Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7).</span><span class="sxs-lookup"><span data-stu-id="1bc4e-108">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="1bc4e-109">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="1bc4e-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="1bc4e-110">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="1bc4e-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bc4e-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="1bc4e-111">Syntax</span></span>  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1bc4e-112">Parameter</span><span class="sxs-lookup"><span data-stu-id="1bc4e-112">Parameters</span></span>  
  
|<span data-ttu-id="1bc4e-113">Argument</span><span class="sxs-lookup"><span data-stu-id="1bc4e-113">Argument</span></span>|<span data-ttu-id="1bc4e-114">description</span><span class="sxs-lookup"><span data-stu-id="1bc4e-114">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="1bc4e-115">Der Name eines X.509-Zertifikats, das in die SPC-Datei eingebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-115">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="1bc4e-116">Sie können mehrere Namen angeben, die durch Leerzeichen voneinander getrennt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-116">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="1bc4e-117">Der Name einer Zertifikatssperrliste, die in die SPC-Datei aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-117">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="1bc4e-118">Sie können mehrere Namen angeben, die durch Leerzeichen voneinander getrennt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-118">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="1bc4e-119">Der Name des PKCS #7-Objekts, das die X.509-Zertifikate enthält.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-119">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="1bc4e-120">Option</span><span class="sxs-lookup"><span data-stu-id="1bc4e-120">Option</span></span>|<span data-ttu-id="1bc4e-121">description</span><span class="sxs-lookup"><span data-stu-id="1bc4e-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1bc4e-122">**/?**</span><span class="sxs-lookup"><span data-stu-id="1bc4e-122">**/?**</span></span>|<span data-ttu-id="1bc4e-123">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-123">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="1bc4e-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="1bc4e-124">Examples</span></span>  
 <span data-ttu-id="1bc4e-125">Der folgende Befehl erstellt ein SPC aus `myCertificate.cer` und platziert es in `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-125">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="1bc4e-126">Der folgende Befehl erstellt ein SPC aus `oneCertificate.cer` und `twoCertificate.cer` und platziert es in `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="1bc4e-126">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="1bc4e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1bc4e-127">See Also</span></span>  
 [<span data-ttu-id="1bc4e-128">Extras</span><span class="sxs-lookup"><span data-stu-id="1bc4e-128">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="1bc4e-129">Makecert.exe (Tool für die Zertifikaterstellung)</span><span class="sxs-lookup"><span data-stu-id="1bc4e-129">Makecert.exe (Certificate Creation Tool)</span></span>](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d)  
 [<span data-ttu-id="1bc4e-130">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="1bc4e-130">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
