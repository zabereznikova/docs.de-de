---
title: Find Private Key-Tool (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 8f156cbb2f4fad8d51e356bd4dee2d72d9397ffb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929583"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="931fb-102">Find Private Key-Tool (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="931fb-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="931fb-103">Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="931fb-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="931fb-104">Z. B. *FindPrivateKey.exe* kann verwendet werden, finden Sie den Speicherort und Namen der privaten Schlüsseldatei mit einem bestimmten x. 509-Zertifikat im Zertifikatspeicher verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="931fb-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="931fb-105">Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="931fb-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="931fb-106">Weitere Informationen, wo Sie das Beispiel zu finden und wie diese erstellt werden, finden Sie unter [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="931fb-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="931fb-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="931fb-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="931fb-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="931fb-108">Remarks</span></span>

<span data-ttu-id="931fb-109">In den folgenden Tabellen werden die Argumente und Optionen beschrieben, die mit dem Find Private Key-Tool (FindPrivateKey.exe) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="931fb-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="931fb-110">Argument</span><span class="sxs-lookup"><span data-stu-id="931fb-110">Argument</span></span>|<span data-ttu-id="931fb-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="931fb-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="931fb-112">Der Name des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="931fb-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="931fb-113">Der Speicherort des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="931fb-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="931fb-114">Option</span><span class="sxs-lookup"><span data-stu-id="931fb-114">Option</span></span>|<span data-ttu-id="931fb-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="931fb-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="931fb-116">`/n <` *subjectName* `>`</span><span class="sxs-lookup"><span data-stu-id="931fb-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="931fb-117">Gibt den Betreffnamen des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="931fb-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="931fb-118">`/t <` *thumbprint* `>`</span><span class="sxs-lookup"><span data-stu-id="931fb-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="931fb-119">Gibt den Fingerabdruck des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="931fb-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="931fb-120">Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.</span><span class="sxs-lookup"><span data-stu-id="931fb-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="931fb-121">Gibt nur den Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="931fb-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="931fb-122">Gibt nur das Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="931fb-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="931fb-123">Gibt nur den absoluten Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="931fb-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="931fb-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="931fb-124">Examples</span></span>

<span data-ttu-id="931fb-125">Der folgende Befehl ruft den privaten Schlüssel für John Doe:</span><span class="sxs-lookup"><span data-stu-id="931fb-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="931fb-126">Der folgende Befehl ruft den privaten Schlüssel für den lokalen Computer:</span><span class="sxs-lookup"><span data-stu-id="931fb-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```