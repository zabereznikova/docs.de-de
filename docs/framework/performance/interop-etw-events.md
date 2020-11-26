---
title: Interop-ETW-Ereignisse
description: Überprüfen Sie die Ereignisse der Interop-etw (Ereignis Ablauf Verfolgung für Windows), die Informationen über die MSIL (Microsoft Intermediate Language)-Stub-Generierung & Caching in .net erfassen.
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
ms.openlocfilehash: 8e92a1492d0295fb71473843752cb4c6184d3604
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96242187"
---
# <a name="interop-etw-events"></a>Interop-ETW-Ereignisse

Interop-Ereignisse erfassen Informationen zur MSIL-Stubgenerierung und -Zwischenspeicherung (Microsoft Intermediate Language).  

## <a name="ilstubgenerated-event"></a>ILStubGenerated-Ereignis

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0x2000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|88|Der MSIL-Stub wurde generiert.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt16|Der Modulbezeichner.|  
|StubMethodID|win:UInt64|Der Bezeichner für die Stubmethode.|  
|StubFlags|win:UInt64|Die Flags für den Stub:<br /><br /> 0x1 – Reverse-Interop.<br /><br /> 0x2 – COM-Interop.<br /><br /> 0x4 – Von „NGen.exe“ generierter Stub.<br /><br /> 0x8 – Delegat.<br /><br /> 0x10-Variablen Argument.<br /><br /> 0x20 – Nicht verwalteter Aufgerufener.|  
|ManagedInteropMethodToken|win:UInt32|Das Token für die verwaltete Interop-Methode.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Der Namespace für die verwaltete Interop-Methode.|  
|ManagedInteropMethodName|win:UnicodeString|Der Name der verwalteten Interop-Methode.|  
|ManagedInteropMethodSignature|win:UnicodeString|Die Signatur der verwalteten Interop-Methode.|  
|NativeMethodSignature|win:UnicodeString|Die systemeigene Methodensignatur.|  
|StubMethodSignature|win:UnicodeString|Die Signatur der Stubmethode.|  
|StubMethodILCode|win:UnicodeString|Der MSIL-Code für die Stubmethode.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="ilstubcachehit-event"></a>ILStubCacheHit-Ereignis  

Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0x2000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|89|Es wurde auf den MSIL-Cache zugegriffen.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt16|Der Modulbezeichner.|  
|StubMethodID|win:UInt64|Der Bezeichner für die Stubmethode.|  
|ManagedInteropMethodToken|win:UInt32|Das Token für die verwaltete Interop-Methode.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Der Namespace für die verwaltete Interop-Methode.|  
|ManagedInteropMethodName|win:UnicodeString|Der Name der verwalteten Interop-Methode.|  
|ManagedInteropMethodSignature|win:UnicodeString|Die Signatur der verwalteten Interop-Methode.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
## <a name="see-also"></a>Weitere Informationen

- [CLR-ETW-Ereignisse](clr-etw-events.md)
