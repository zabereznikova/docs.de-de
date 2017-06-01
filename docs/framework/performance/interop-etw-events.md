---
title: "Interop ETW Events | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "interop events [.NET Framework]"
  - "ETW, interop events (CLR)"
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Interop ETW Events
<a name="top"></a> Interop\-Ereignisse erfassen Informationen zur MSIL\-Stubgenerierung und \-Zwischenspeicherung \(Microsoft Intermediate Language\).  
  
 Diese Kategorie umfasst die folgenden Ereignisse:  
  
-   [ILStubGenerated\-Ereignis](#ilstubgenerated_event)  
  
-   [ILStubCacheHit\-Ereignis](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## ILStubGenerated\-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. \(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).\)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|------------------------------------------------|-----------|  
|`InteropKeyword` \(0x2000\)|Information \(4\)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis\-ID|Wird ausgelöst, wenn|  
|--------------|------------------|--------------------------|  
|`ILStubGenerated`|88|Der MSIL\-Stub wurde generiert.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|--------------|--------------|------------------|  
|ModuleID|win:UInt16|Der Modulbezeichner.|  
|StubMethodID|win:UInt64|Der Bezeichner für die Stubmethode.|  
|StubFlags|win:UInt64|Die Flags für den Stub:<br /><br /> 0x1 – Reverse\-Interop.<br /><br /> 0x2 – COM\-Interop.<br /><br /> 0x4 – Von „NGen.exe“ generierter Stub.<br /><br /> 0x8 – Delegat.<br /><br /> 0x10 – Variables Argument.<br /><br /> 0x20 – Nicht verwalteter Aufgerufener.|  
|ManagedInteropMethodToken|win:UInt32|Das Token für die verwaltete Interop\-Methode.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Der Namespace für die verwaltete Interop\-Methode.|  
|ManagedInteropMethodName|win:UnicodeString|Der Name der verwalteten Interop\-Methode.|  
|ManagedInteropMethodSignature|win:UnicodeString|Die Signatur der verwalteten Interop\-Methode.|  
|NativeMethodSignature|win:UnicodeString|Die systemeigene Methodensignatur.|  
|StubMethodSignature|win:UnicodeString|Die Signatur der Stubmethode.|  
|StubMethodILCode|win:UnicodeString|Der MSIL\-Code für die Stubmethode.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
<a name="ilstubcachehit_event"></a>   
## ILStubCacheHit\-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|------------------------------------------------|-----------|  
|`InteropKeyword` \(0x2000\)|Information \(4\)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis\-ID|Wird ausgelöst, wenn|  
|--------------|------------------|--------------------------|  
|`ILStubCacheHit`|89|Es wurde auf den MSIL\-Cache zugegriffen.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|--------------|--------------|------------------|  
|ModuleID|win:UInt16|Der Modulbezeichner.|  
|StubMethodID|win:UInt64|Der Bezeichner für die Stubmethode.|  
|ManagedInteropMethodToken|win:UInt32|Das Token für die verwaltete Interop\-Methode.|  
|ManagedInteropMethodNameSpace|win:UnicodeString|Der Namespace für die verwaltete Interop\-Methode.|  
|ManagedInteropMethodName|win:UnicodeString|Der Name der verwalteten Interop\-Methode.|  
|ManagedInteropMethodSignature|win:UnicodeString|Die Signatur der verwalteten Interop\-Methode.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
## Siehe auch  
 [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md)