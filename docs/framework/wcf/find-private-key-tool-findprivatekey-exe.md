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
