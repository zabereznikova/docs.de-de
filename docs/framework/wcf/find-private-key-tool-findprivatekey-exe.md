---
title: Find Private Key-Tool (FindPrivateKey.exe)
ms.date: 09/11/2017
ms.assetid: b8846a95-3fcc-4e8c-b9c0-128d975a6307
ms.openlocfilehash: 316f55b93cf4d867b99878bf483b73cb3f09ad04
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990349"
---
# <a name="find-private-key-tool-findprivatekeyexe"></a><span data-ttu-id="55fef-102">Find Private Key-Tool (FindPrivateKey.exe)</span><span class="sxs-lookup"><span data-stu-id="55fef-102">Find Private Key Tool (FindPrivateKey.exe)</span></span>

<span data-ttu-id="55fef-103">Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="55fef-103">This command-line tool can be used to retrieve a private key from a certificate store.</span></span> <span data-ttu-id="55fef-104">Mithilfe von *FindPrivateKey. exe* können Sie z. b. den Speicherort und den Namen der privaten Schlüsseldatei suchen, die einem bestimmten X. 509-Zertifikat im Zertifikat Speicher zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="55fef-104">For example, *FindPrivateKey.exe* can be used to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55fef-105">Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="55fef-105">The FindPrivateKey tool is shipped as a WCF sample.</span></span> <span data-ttu-id="55fef-106">Weitere Informationen dazu, wo Sie das Beispiel finden und wie Sie es erstellen, finden Sie unter [FindPrivateKey](./samples/findprivatekey.md).</span><span class="sxs-lookup"><span data-stu-id="55fef-106">For more information about where to find the sample and how to build it, see [FindPrivateKey](./samples/findprivatekey.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="55fef-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="55fef-107">Syntax</span></span>

```console
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a><span data-ttu-id="55fef-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55fef-108">Remarks</span></span>

<span data-ttu-id="55fef-109">In den folgenden Tabellen werden die Argumente und Optionen beschrieben, die mit dem Find Private Key-Tool (FindPrivateKey.exe) verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="55fef-109">The following tables describe the arguments and the options that can be used with the Find Private Key tool (FindPrivateKey.exe).</span></span>

|<span data-ttu-id="55fef-110">Argument</span><span class="sxs-lookup"><span data-stu-id="55fef-110">Argument</span></span>|<span data-ttu-id="55fef-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55fef-111">Description</span></span>|
|--------------|-----------------|
|`storeName`|<span data-ttu-id="55fef-112">Der Name des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="55fef-112">Name of the certificate store.</span></span>|
|`storeLocation`|<span data-ttu-id="55fef-113">Der Speicherort des Zertifikatspeichers.</span><span class="sxs-lookup"><span data-stu-id="55fef-113">The location of the certificate store.</span></span>|

|<span data-ttu-id="55fef-114">Option</span><span class="sxs-lookup"><span data-stu-id="55fef-114">Option</span></span>|<span data-ttu-id="55fef-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55fef-115">Description</span></span>|
|------------|-----------------|
|<span data-ttu-id="55fef-116">`/n <` *subjectName* `>`</span><span class="sxs-lookup"><span data-stu-id="55fef-116">`/n <` *subjectName* `>`</span></span>|<span data-ttu-id="55fef-117">Gibt den Betreffnamen des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="55fef-117">Specifies the subject name of the certificate.</span></span>|
|<span data-ttu-id="55fef-118">`/t <`Finger *Abdruck*`>`</span><span class="sxs-lookup"><span data-stu-id="55fef-118">`/t <` *thumbprint* `>`</span></span>|<span data-ttu-id="55fef-119">Gibt den Fingerabdruck des Zertifikats an.</span><span class="sxs-lookup"><span data-stu-id="55fef-119">Specifies the thumbprint of the certificate.</span></span> <span data-ttu-id="55fef-120">Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.</span><span class="sxs-lookup"><span data-stu-id="55fef-120">Use Certmgr.exe to retrieve the thumbprint of the certificate.</span></span>|
|`/f`|<span data-ttu-id="55fef-121">Gibt nur den Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="55fef-121">Outputs the file name only.</span></span>|
|`/d`|<span data-ttu-id="55fef-122">Gibt nur das Verzeichnis aus.</span><span class="sxs-lookup"><span data-stu-id="55fef-122">Outputs the directory only.</span></span>|
|`/a`|<span data-ttu-id="55fef-123">Gibt nur den absoluten Dateinamen aus.</span><span class="sxs-lookup"><span data-stu-id="55fef-123">Outputs the absolute file name.</span></span>|

## <a name="examples"></a><span data-ttu-id="55fef-124">Beispiele</span><span class="sxs-lookup"><span data-stu-id="55fef-124">Examples</span></span>

<span data-ttu-id="55fef-125">Mit dem folgenden Befehl wird der private Schlüssel für John Doe abgerufen:</span><span class="sxs-lookup"><span data-stu-id="55fef-125">The following command retrieves the private key for John Doe:</span></span>

```console
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

<span data-ttu-id="55fef-126">Der folgende Befehl ruft den privaten Schlüssel für den lokalen Computer ab:</span><span class="sxs-lookup"><span data-stu-id="55fef-126">The following command retrieves the private key for the local machine:</span></span>

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
