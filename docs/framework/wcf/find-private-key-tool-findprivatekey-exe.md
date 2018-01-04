---
title: Find Private Key-Tool (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bdfa1a9e45332e8c2acbbc8cd8a09bd2f927fbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="f0495-102">Find Private Key-Tool (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="f0495-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="f0495-103">Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f0495-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="f0495-104">Beispielsweise *FindPrivateKey.exe* kann verwendet werden, um den Speicherort und Namen der privaten Schlüsseldatei, die ein bestimmtes x. 509-Zertifikat im Zertifikatspeicher zugeordnet zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f0495-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0495-105">Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="f0495-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="f0495-106">Weitere Informationen zu, wo Sie das Beispiel zu finden und wie Sie es erstellen, finden Sie unter [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="f0495-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="f0495-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0495-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="f0495-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0495-108">Remarks</span></span>

<span data-ttu-id="f0495-109">In den folgenden Tabellen werden die Argumente und Optionen beschrieben, die mit dem Find Private Key-Tool (FindPrivateKey.exe) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f0495-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="f0495-110">Argument</span><span class="sxs-lookup"><span data-stu-id="f0495-110">Argument</span></span>|<span data-ttu-id="f0495-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0495-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="f0495-112">Der Name des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="f0495-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="f0495-113">Der Speicherort des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="f0495-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="f0495-114">Option</span><span class="sxs-lookup"><span data-stu-id="f0495-114">Option</span></span>|<span data-ttu-id="f0495-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0495-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="f0495-116">`/n <`*SubjectName*`>`</span><span class="sxs-lookup"><span data-stu-id="f0495-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="f0495-117">Gibt den Betreffnamen des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="f0495-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="f0495-118">`/t <`*Fingerabdruck*`>`</span><span class="sxs-lookup"><span data-stu-id="f0495-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="f0495-119">Gibt den Fingerabdruck des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="f0495-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="f0495-120">Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f0495-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="f0495-121">Gibt nur den Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="f0495-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="f0495-122">Gibt nur das Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="f0495-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="f0495-123">Gibt nur den absoluten Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="f0495-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="f0495-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f0495-124">Examples</span></span>

<span data-ttu-id="f0495-125">Der folgende Befehl wird der private Schlüssel für John Doe abgerufen:</span><span class="sxs-lookup"><span data-stu-id="f0495-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="f0495-126">Der folgende Befehl ruft den privaten Schlüssel für den lokalen Computer ab:</span><span class="sxs-lookup"><span data-stu-id="f0495-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```