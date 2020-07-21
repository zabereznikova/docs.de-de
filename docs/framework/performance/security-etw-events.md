---
title: ETW-Sicherheitsereignisse
description: Informieren Sie sich über Sicherheits-ETW-Ereignisse, die bei der Überprüfung starker Namen und bei der authenticodeüberprüfung in .net ausgelöst werden
ms.date: 03/30/2017
helpviewer_keywords:
- security events [.NET Framework]
- ETW, security events (CLR)
ms.assetid: 0ed69f73-5c01-4514-bd63-979c6e38d41d
ms.openlocfilehash: 2fd2d450223cd16a7791b8f6c67afe6bcb954eb3
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474214"
---
# <a name="security-etw-events"></a>ETW-Sicherheitsereignisse

Sicherheitsereignisse werden während der Überprüfung mit starkem Namen und bei der Authenticodeüberprüfung ausgelöst.  

## <a name="strongnameverificationstart_v1-and-strongnameverificationstop_v1-events"></a>StrongNameVerificationStart_V1-Ereignis und StrongNameVerificationStop_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0 x 400)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`StrongNameVerificationStart_V1`|181|Beginn der Überprüfung mit starkem Namen.|  
|`StrongNameVerificationStop_V1`|182|Ende der Überprüfung mit starkem Namen.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Die Überprüfungsflags.|  
|ErrorCode|win:UInt32|Der HResult-Fehlercode.|  
|FullyQualifiedAssemblyName|win:UnicodeString|Der vollqualifizierte Assemblyname.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  

## <a name="authenticodeverificationstart_v1-and-authenticodeverificationstop_v1-events"></a>AuthenticodeVerificationStart_V1-Ereignis und AuthenticodeVerificationStop_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`SecurityKeyword` (0 x 400)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`AuthenticodeVerificationStart_V1`|183|Beginn der Authenticodeüberprüfung.|  
|`AuthenticodeVerificationStop_V1`|184|Ende der Authenticodeüberprüfung.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|VerificationFlags|win:UInt32|Die Überprüfungsflags.|  
|ErrorCode|win:UInt32|Der HResult-Fehlercode.|  
|ModulePath|win:UnicodeString|Der Modulpfad.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="see-also"></a>Weitere Informationen

- [CLR-ETW-Ereignisse](clr-etw-events.md)
