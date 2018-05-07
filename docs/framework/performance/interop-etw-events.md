---
title: Interop-ETW-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bc9a90e9d889673d8f67e4f9158edebcb65235b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="interop-etw-events"></a>Interop-ETW-Ereignisse
<a name="top"></a> Interop-Ereignisse erfassen Informationen zur MSIL-Stubgenerierung und -Zwischenspeicherung (Microsoft Intermediate Language).  
  
 Diese Kategorie umfasst die folgenden Ereignisse:  
  
-   [ILStubGenerated-Ereignis](#ilstubgenerated_event)  
  
-   [ILStubCacheHit-Ereignis](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a>ILStubGenerated-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`InteropKeyword` (0x2000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|88|Der MSIL-Stub wurde generiert.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt16|Der Modulbezeichner.|  
|StubMethodID|win:UInt64|Der Bezeichner für die Stubmethode.|  
|StubFlags|win:UInt64|Die Flags für den Stub:<br /><br /> 0x1 – Reverse-Interop.<br /><br /> 0x2 – COM-Interop.<br /><br /> 0x4 – Von „NGen.exe“ generierter Stub.<br /><br /> 0x8 – Delegat.<br /><br /> 0x10 – Variables Argument.<br /><br /> 0x20 – Nicht verwalteter Aufgerufener.|  
|ManagedInteropMethodToken|win:UInt32|Das Token für die verwaltete Interop-Methode.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Der Namespace für die verwaltete Interop-Methode.|  
|ManagedInteropMethodName|win:UnicodeString|Der Name der verwalteten Interop-Methode.|  
|ManagedInteropMethodSignature|win:UnicodeString|Die Signatur der verwalteten Interop-Methode.|  
|NativeMethodSignature|win:UnicodeString|Die systemeigene Methodensignatur.|  
|StubMethodSignature|win:UnicodeString|Die Signatur der Stubmethode.|  
|StubMethodILCode|win:UnicodeString|Der MSIL-Code für die Stubmethode.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück zum Anfang](#top)  
  
<a name="ilstubcachehit_event"></a>   
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
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|ModuleID|win:UInt16|Der Modulbezeichner.|  
|StubMethodID|win:UInt64|Der Bezeichner für die Stubmethode.|  
|ManagedInteropMethodToken|win:UInt32|Das Token für die verwaltete Interop-Methode.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Der Namespace für die verwaltete Interop-Methode.|  
|ManagedInteropMethodName|win:UnicodeString|Der Name der verwalteten Interop-Methode.|  
|ManagedInteropMethodSignature|win:UnicodeString|Die Signatur der verwalteten Interop-Methode.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück zum Anfang](#top)  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)
