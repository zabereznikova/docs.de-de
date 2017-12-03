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
# <a name="find-private-key-tool-findprivatekeyexe"></a>Find Private Key-Tool (FindPrivateKey.exe)
Mit diesem Befehlszeilentool kann ein privater Schlüssel aus einem Zertifikatspeicher abgerufen werden. FindPrivateKey.exe kann beispielsweise verwendet werden, um den Speicherort und Namen der privaten Schlüsseldatei zu finden, die mit einem bestimmten X.509-Zertifikat im Zertifikatspeicher verknüpft ist.  
  
> [!IMPORTANT]
>  Das FindPrivateKey-Tool wird als WCF-Beispiel zur Verfügung gestellt. Weitere Informationen dazu, wo Sie das Beispiel finden und wie Sie es erstellen, finden Sie unter  
  
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
 Mit dem folgenden Befehl wird der private Schlüssel für John Doe abgerufen.  
  
```  
FindPrivateKey My CurrentUser -n "CN=John Doe"  
```  
  
 Mit dem folgenden Befehl wird der private Schlüssel für den lokalen Computer abgerufen.  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –a  
```
