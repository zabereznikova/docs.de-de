---
title: Find Private Key-Tool (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 8f156cbb2f4fad8d51e356bd4dee2d72d9397ffb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498513"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="45675-102">Find Private Key-Tool (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="45675-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="45675-103">Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="45675-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="45675-104">Beispielsweise *FindPrivateKey.exe* kann verwendet werden, um den Speicherort und Namen der privaten Schlüsseldatei, die ein bestimmtes x. 509-Zertifikat im Zertifikatspeicher zugeordnet zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="45675-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="45675-105">Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="45675-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="45675-106">Weitere Informationen zu, wo Sie das Beispiel zu finden und wie Sie es erstellen, finden Sie unter [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="45675-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="45675-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="45675-107">Syntax</span></span>

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="45675-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45675-108">Remarks</span></span>

<span data-ttu-id="45675-109">In den folgenden Tabellen werden die Argumente und Optionen beschrieben, die mit dem Find Private Key-Tool (FindPrivateKey.exe) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="45675-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="45675-110">Argument</span><span class="sxs-lookup"><span data-stu-id="45675-110">Argument</span></span>|<span data-ttu-id="45675-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45675-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="45675-112">Der Name des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="45675-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="45675-113">Der Speicherort des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="45675-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="45675-114">Option</span><span class="sxs-lookup"><span data-stu-id="45675-114">Option</span></span>|<span data-ttu-id="45675-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45675-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="45675-116">`/n <` *subjectName* `>`</span><span class="sxs-lookup"><span data-stu-id="45675-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="45675-117">Gibt den Betreffnamen des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="45675-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="45675-118">`/t <` *Fingerabdruck* `>`</span><span class="sxs-lookup"><span data-stu-id="45675-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="45675-119">Gibt den Fingerabdruck des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="45675-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="45675-120">Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.</span><span class="sxs-lookup"><span data-stu-id="45675-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="45675-121">Gibt nur den Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="45675-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="45675-122">Gibt nur das Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="45675-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="45675-123">Gibt nur den absoluten Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="45675-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="45675-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="45675-124">Examples</span></span>

<span data-ttu-id="45675-125">Der folgende Befehl wird der private Schlüssel für John Doe abgerufen:</span><span class="sxs-lookup"><span data-stu-id="45675-125">The following command retrieves the private key for John Doe:</span></span>

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="45675-126">Der folgende Befehl ruft den privaten Schlüssel für den lokalen Computer ab:</span><span class="sxs-lookup"><span data-stu-id="45675-126">The following command retrieves the private key for the local machine:</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```