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
ms.openlocfilehash: 2d515077106b8f0527d045d5ef7fb6d7c0c7aa62
ms.sourcegitcommit: 9bee08539b1886c9d57fa3d5bd8a58dfdd7cad94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2017
---
# <a name="find-private-key-tool-findprivatekeyexe"></a>Find Private Key-Tool (FindPrivateKey.exe)

Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden. Beispielsweise *FindPrivateKey.exe* kann verwendet werden, um den Speicherort und Namen der privaten Schlüsseldatei, die ein bestimmtes x. 509-Zertifikat im Zertifikatspeicher zugeordnet zu ermitteln.

> [!IMPORTANT]
> Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt. Weitere Informationen zu, wo Sie das Beispiel zu finden und wie Sie es erstellen, finden Sie unter [FindPrivateKey](./samples/findprivatekey.md).

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
|`/n <`*SubjectName*`>`|Gibt den Betreffnamen des Zertifikats an.|
|`/t <`*Fingerabdruck*`>`|Gibt den Fingerabdruck des Zertifikats an. Verwenden Sie Certmgr.exe, um den Fingerabdruck des Zertifikats abzurufen.|
|`/f`|Gibt nur den Dateinamen aus.|
|`/d`|Gibt nur das Verzeichnis aus.|
|`/a`|Gibt nur den absoluten Dateinamen aus.|

## <a name="examples"></a>Beispiele

Der folgende Befehl wird der private Schlüssel für John Doe abgerufen:

```
FindPrivateKey My CurrentUser -n "CN=John Doe"
```

Der folgende Befehl ruft den privaten Schlüssel für den lokalen Computer ab:

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a
```