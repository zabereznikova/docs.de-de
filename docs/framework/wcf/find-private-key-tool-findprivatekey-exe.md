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
# <a name="find-private-key-tool-findprivatekeyexe"></a>Find Private Key-Tool (FindPrivateKey.exe)

Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden. Z. B. *FindPrivateKey.exe* kann verwendet werden, finden Sie den Speicherort und Namen der privaten Schlüsseldatei mit einem bestimmten x. 509-Zertifikat im Zertifikatspeicher verknüpft ist.

> [!IMPORTANT]
> Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt. Weitere Informationen, wo Sie das Beispiel zu finden und wie diese erstellt werden, finden Sie unter [FindPrivateKey](./samples/findprivatekey.md).

## <a name="syntax"></a>Syntax

```
FindPrivateKey<storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

## <a name="remarks"></a>Hinweise

In den folgenden Tabellen werden die Argumente und Optionen beschrieben, die mit dem Find Private Key-Tool (FindPrivateKey.exe) verwendet werden können.

|Argument|Beschreibung|
|--------------|-----------------|
|`storeName`|Der Name des Zertifikatspeichers.|
|`storeLocation`|Der Speicherort des Zertifikatspeichers.|

|Option|Beschreibung|
|------------|-----------------|
|`/n <` *subjectName* `>`|Gibt den Betreffnamen des Zertifikats an.|
|`/t <` *thumbprint* `>`|Gibt den Fingerabdruck des Zertifikats an. Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.|
|`/f`|Gibt nur den Dateinamen aus.|
|`/d`|Gibt nur das Verzeichnis aus.|
|`/a`|Gibt nur den absoluten Dateinamen aus.|

## <a name="examples"></a>Beispiele

Der folgende Befehl ruft den privaten Schlüssel für John Doe:

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

Der folgende Befehl ruft den privaten Schlüssel für den lokalen Computer:

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```