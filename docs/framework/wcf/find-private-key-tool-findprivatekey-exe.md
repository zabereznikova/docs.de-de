---
title: Find Private Key-Tool (FindPrivateKey.exe)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f542e0ba3bf35319c270fe9f93d3f355cc45ac95
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="74f64-102">Find Private Key-Tool (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="74f64-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>
<span data-ttu-id="74f64-103">Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="74f64-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="74f64-104">FindPrivateKey.exe kann beispielsweise verwendet werden, um den Speicherort und Namen der privaten Schlüsseldatei zu finden, die mit einem bestimmten X.509-Zertifikat im Zertifikatspeicher verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="74f64-104">For example, FindPrivateKey.exe can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74f64-105">Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="74f64-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="74f64-106">Weitere Informationen dazu, wo Sie das Beispiel finden und wie Sie es erstellen, finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="74f64-106">For more information about where to find the sample and how to build it, see</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74f64-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="74f64-107">Syntax</span></span>  
  
```  
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
## <a name="remarks"></a><span data-ttu-id="74f64-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74f64-108">Remarks</span></span>  
 <span data-ttu-id="74f64-109">In den folgenden Tabellen werden die Argumente und Optionen beschrieben, die mit dem Find Private Key-Tool (FindPrivateKey.exe) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="74f64-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>  
  
|<span data-ttu-id="74f64-110">Argument</span><span class="sxs-lookup"><span data-stu-id="74f64-110">Argument</span></span>|<span data-ttu-id="74f64-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74f64-111">Description</span></span>|  
|--------------|-----------------|  
|`storeName`|<span data-ttu-id="74f64-112">Der Name des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="74f64-112">Name of the certificate store.</span></span>|  
|`storeLocation`|<span data-ttu-id="74f64-113">Der Speicherort des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="74f64-113">The location of the certificate store.</span></span>|  
  
|<span data-ttu-id="74f64-114">Option</span><span class="sxs-lookup"><span data-stu-id="74f64-114">Option</span></span>|<span data-ttu-id="74f64-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74f64-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="74f64-116">`/n <`*SubjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="74f64-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="74f64-117">Gibt den Betreffnamen des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="74f64-117">Specifies the subject name of the certificate.</span></span>|  
|<span data-ttu-id="74f64-118">`/t <`*Fingerabdruck*`>`</span><span class="sxs-lookup"><span data-stu-id="74f64-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="74f64-119">Gibt den Fingerabdruck des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="74f64-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="74f64-120">Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.</span><span class="sxs-lookup"><span data-stu-id="74f64-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|  
|`/f`|<span data-ttu-id="74f64-121">Gibt nur den Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="74f64-121">Outputs the file name only.</span></span>|  
|`/d`|<span data-ttu-id="74f64-122">Gibt nur das Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="74f64-122">Outputs the directory only.</span></span>|  
|`/a`|<span data-ttu-id="74f64-123">Gibt nur den absoluten Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="74f64-123">Outputs the absolute file name.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="74f64-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="74f64-124">Examples</span></span>  
 <span data-ttu-id="74f64-125">Mit dem folgenden Befehl wird der private Schlüssel für John Doe abgerufen.</span><span class="sxs-lookup"><span data-stu-id="74f64-125">The following command retrieves the private key for John Doe.</span></span>  
  
```  
FindPrivateKey My CurrentUser -n "CN=John Doe"  
```  
  
 <span data-ttu-id="74f64-126">Mit dem folgenden Befehl wird der private Schlüssel für den lokalen Computer abgerufen.</span><span class="sxs-lookup"><span data-stu-id="74f64-126">The following command retrieves the private key for the local machine.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a  
```
