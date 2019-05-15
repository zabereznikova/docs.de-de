---
title: Find Private Key-Tool (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 00ad27d28ee3a589d5ee8702bd036b05d8ceb4b3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637575"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="2bf05-102">Find Private Key-Tool (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="2bf05-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="2bf05-103">Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="2bf05-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="2bf05-104">Z. B. *FindPrivateKey.exe* kann verwendet werden, finden Sie den Speicherort und Namen der privaten Schlüsseldatei mit einem bestimmten x. 509-Zertifikat im Zertifikatspeicher verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="2bf05-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2bf05-105">Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="2bf05-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="2bf05-106">Weitere Informationen, wo Sie das Beispiel zu finden und wie diese erstellt werden, finden Sie unter [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="2bf05-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="2bf05-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bf05-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="2bf05-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2bf05-108">Remarks</span></span>

<span data-ttu-id="2bf05-109">In den folgenden Tabellen werden die Argumente und Optionen beschrieben, die mit dem Find Private Key-Tool (FindPrivateKey.exe) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="2bf05-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="2bf05-110">Argument</span><span class="sxs-lookup"><span data-stu-id="2bf05-110">Argument</span></span>|<span data-ttu-id="2bf05-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bf05-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="2bf05-112">Der Name des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="2bf05-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="2bf05-113">Der Speicherort des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="2bf05-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="2bf05-114">Option</span><span class="sxs-lookup"><span data-stu-id="2bf05-114">Option</span></span>|<span data-ttu-id="2bf05-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bf05-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="2bf05-116">`/n <` *subjectName* `>`</span><span class="sxs-lookup"><span data-stu-id="2bf05-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="2bf05-117">Gibt den Betreffnamen des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="2bf05-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="2bf05-118">`/t <` *thumbprint* `>`</span><span class="sxs-lookup"><span data-stu-id="2bf05-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="2bf05-119">Gibt den Fingerabdruck des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="2bf05-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="2bf05-120">Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2bf05-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="2bf05-121">Gibt nur den Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="2bf05-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="2bf05-122">Gibt nur das Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="2bf05-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="2bf05-123">Gibt nur den absoluten Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="2bf05-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="2bf05-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2bf05-124">Examples</span></span>

<span data-ttu-id="2bf05-125">Der folgende Befehl ruft den privaten Schlüssel für John Doe:</span><span class="sxs-lookup"><span data-stu-id="2bf05-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="2bf05-126">Der folgende Befehl ruft den privaten Schlüssel für den lokalen Computer:</span><span class="sxs-lookup"><span data-stu-id="2bf05-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
