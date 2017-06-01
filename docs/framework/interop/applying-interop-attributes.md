---
title: "Applying Interop Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "design-time attributes"
  - ".NET Framework, exposing components to COM"
  - "attributes [.NET Framework], design-time functionality"
  - "conversion-tool attributes"
  - "attributes [.NET Framework], interop-specific"
  - "attributes [.NET Framework], conversion-tool"
  - "interoperation with unmanaged code, applying attributes"
  - "interoperation with unmanaged code, exposing .NET Framework components"
  - "COM interop, exposing COM components"
  - "COM interop, applying attributes"
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Applying Interop Attributes
Der <xref:System.Runtime.InteropServices>\-Namespace unterscheidet drei Kategorien von Interop\-spezifischen Attributen: Attribute, die Sie während der Entwurfszeit zugewiesen haben, Attribute, die durch COM\-Interop\-Tools und APIs beim Konvertierungsprozess zugewiesen wurden, sowie Attribute, die entweder von Ihnen oder von COM\-Interop zugewiesen wurden.  
  
 Weitere Informationen, wie Sie verwaltetem Code Attribute zuweisen können, finden Sie unter [Erweitern von Metadaten mithilfe von Attributen](../../../docs/standard/attributes/index.md).  Interop\-spezifische Attributen lassen sich Typen, Methoden, Eigenschaften, Parametern, Feldern und anderen Membern in gleicher Weise zuweisen wie andere benutzerdefinierte Attribute.  
  
## Entwurfszeitattribute  
 Zum Anpassen des Ergebnisses des Konvertierungsprozesses, der von COM\-Interop\-Tools und APIs durchgeführt wird, können Sie Entwurfszeitattribute verwenden.  In der folgenden Tabelle werden die Attribute beschrieben, die Sie dem verwalteten Quellcode zuweisen können.  Die hier beschriebenen Attribute können gegebenenfalls auch von COM\-Interop\-Tools zugewiesen werden.  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|Gibt an, ob der Typ mit dem Automatisierungsmarshaller oder mit benutzerdefiniertem Proxy und Stub gemarshallt werden soll.|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|Steuert den Schnittstellentyp, der für eine Klasse generiert wird.|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|Bezeichnet die CLSID der ursprünglichen Co\-Klasse, die aus einer Typbibliothek importiert wurde.<br /><br /> Dieses Attribut wird üblicherweise von COM\-Interop\-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|Gibt an, dass eine Co\-Klassen\- oder Schnittstellendefinition aus einer COM\-Typbibliothek importiert wurde.  Dieses von Common Language Runtime verwendete Flag zeigt an, wie der Typ aktiviert und gemarshallt wird.  Dieses Attribut verhindert, dass der Typ zurück in eine Typbibliothek exportiert wird.<br /><br /> Dieses Attribut wird üblicherweise von COM\-Interop\-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|Zeigt an, dass eine Methode aufgerufen werden soll, wenn die Assembly für die Verwendung von COM registriert wird. Dadurch kann durch den Benutzer erstellter Code während der Registrierung ausgeführt werden.|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|Bezeichnet Schnittstellen, welche Ereignisquellen für die Klasse darstellen.<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|Zeigt an, dass eine Methode aufgerufen werden soll, wenn die COM\-Registrierung der Assembly aufgehoben wird. Dadurch kann durch den Benutzer erstellter Code während des Prozesses ausgeführt werden.|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|Macht Typen für COM unsichtbar, wenn der Attributwert **false** lautet.  Dieses Attribut zum Steuern der Sichtbarkeit in COM kann einem einzelnen Typ oder einer ganzen Assembly zugewiesen werden.  Standardmäßig sind alle verwalteten, öffentlichen Typen sichtbar, d. h. das Attribut ist zur Anzeige nicht erforderlich.|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|Bestimmt den COM\-Dispatchbezeichner \(DISPID, Dispatch Identifier\) für eine Methode oder ein Feld.  Dieses Attribut enthält den DISPID für die beschriebene Methode, das Feld oder die Eigenschaft.<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|Bestimmt die physische Position der einzelnen Felder in einer Klasse \(wird zusammen mit **StructLayoutAttribute** verwendet, wenn unter **LayoutKind** die Option `Explicit` eingestellt ist\).|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|Gibt den globalen eindeutigen Bezeichner \(GUID, Globally Unique Identifier\) einer Klasse, einer Schnittstelle oder einer ganzen Typbibliothek an.  Die an das Attribut übergebene Zeichenfolge muss in einem Format vorliegen, das einem zulässigen Konstruktorargument für den Typ **System.Guid** entspricht.<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
|[IDispatchImpAttribute](frlrfsystemruntimeinteropservicesidispatchimplattributeclasstopic)|Gibt an, welche **IDispatch**\-Schnittstellenimplementierung von Common Language Runtime verwendet wird, um duale oder Dispatch\-Schnittstellen für COM verfügbar zu machen.|  
|<xref:System.Runtime.InteropServices.InAttribute>|Gibt an, dass die Daten in den Aufrufer gemarshallt werden sollen.  Kann zum Festlegen von Attributen für Parameter verwendet werden.|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|Bestimmt, wie eine verwaltete Schnittstelle für COM\-Clients verfügbar gemacht wird \(**Dual**, abgeleitet von **IUnknown** oder nur `IDispatch`\).<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|Zeigt an, dass für eine nicht verwaltete Methodensignatur ein LCID\-Parameter erwartet wird.<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|Bestimmt, wie die Daten in Feldern oder Parametern zwischen verwaltetem und nicht verwaltetem Code gemarshallt werden.  Dieses Attribut ist stets optional, weil jeder Datentyp ein standardmäßiges Marshallverhalten aufweist.<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|Gibt an, dass ein Parameter optional ist.<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
|<xref:System.Runtime.InteropServices.OutAttribute>|Gibt an, dass die Daten in einem Feld oder Parameter von einem aufgerufenen Objekt zurück an dessen Aufrufer gemarshallt werden sollen.|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|Unterdrückt die Transformation einer HRESULT\- oder retval\-Signatur, die normalerweise während Aufrufen zur Interoperation durchgeführt wird.  Das Attribut wirkt sich sowohl beim Marshallen als auch beim Exportieren der Typbibliothek aus.<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|Bestimmt die ProgID einer .NET Framework\-Klasse.  Kann zum Festlegen von Attributen für Klassen verwendet werden.|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|Steuert das physische Layout der Felder einer Klasse.<br /><br /> Dieses Attribut kann von COM\-Interop\-Tools zugewiesen werden.|  
  
## Attribute des Konvertierungstools  
 In der folgenden Tabelle werden Attribute beschrieben, die COM\-Interop\-Tools beim Konvertierungsprozess anwenden.  Diese Attribute können nicht während der Entwurfszeit zugewiesen werden.  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|Gibt den COM\-Alias für einen Parameter oder Feldtyp an.  Kann auf Attributparameter, Felder oder Rückgabewerte angewendet werden.|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|Gibt an, dass Klassen\- oder Schnittstelleninformationen beim Import aus einer Typbibliothek in eine Assembly verloren gegangen sind.|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|Bezeichnet die Quellschnittstelle und die Klasse, die die Methoden der Ereignisschnittstelle implementiert.|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|Gibt an, dass die Assembly ursprünglich aus einer COM\-Typbibliothek importiert wurde.  Dieses Attribut enthält die Typbibliotheksdefinition der ursprünglichen Typbibliothek.|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|Enthält die **FUNCFLAGS**, die ursprünglich für diese Funktion aus der COM\-Typbibliothek importiert wurden.|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|Enthält die **TYPEFLAGS**, die ursprünglich für diesen Typ aus der COM\-Typbibliothek importiert wurden.|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|Enthält die **VARFLAGS**, die ursprünglich für diese Variable aus der COM\-Typbibliothek importiert wurden.|  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices>   
 [Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Attribute](../../../docs/standard/attributes/index.md)   
 [Qualifying .NET Types for Interoperation](../../../docs/framework/interop/qualifying-net-types-for-interoperation.md)   
 [Packaging an Assembly for COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)