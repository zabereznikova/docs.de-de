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
# <a name="find-private-key-tool-findprivatekeyexe"></a>Find Private Key-Tool (FindPrivateKey.exe)

Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden. Mithilfe von *FindPrivateKey. exe* können Sie z. b. den Speicherort und den Namen der privaten Schlüsseldatei suchen, die einem bestimmten X. 509-Zertifikat im Zertifikat Speicher zugeordnet ist.

> [!IMPORTANT]
> Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt. Weitere Informationen dazu, wo Sie das Beispiel finden und wie Sie es erstellen, finden Sie unter [FindPrivateKey](./samples/findprivatekey.md).

## <a name="syntax"></a>Syntax

```console
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
|`/t <`Finger *Abdruck*`>`|Gibt den Fingerabdruck des Zertifikats an. Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.|
|`/f`|Gibt nur den Dateinamen aus.|
|`/d`|Gibt nur das Verzeichnis aus.|
|`/a`|Gibt nur den absoluten Dateinamen aus.|

## <a name="examples"></a>Beispiele

Mit dem folgenden Befehl wird der private Schlüssel für John Doe abgerufen:

```console
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

Der folgende Befehl ruft den privaten Schlüssel für den lokalen Computer ab:

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```
