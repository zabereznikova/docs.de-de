---
title: Anwenden von Interop-Attributen
ms.date: 03/30/2017
helpviewer_keywords:
- design-time attributes
- .NET Framework, exposing components to COM
- attributes [.NET Framework], design-time functionality
- conversion-tool attributes
- attributes [.NET Framework], interop-specific
- attributes [.NET Framework], conversion-tool
- interoperation with unmanaged code, applying attributes
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
- COM interop, applying attributes
ms.assetid: b6014613-641c-4912-9e2f-83a99210a037
ms.openlocfilehash: ca104c512641774217de5e270dc50b7393fc5725
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159246"
---
# <a name="applying-interop-attributes"></a>Anwenden von Interop-Attributen
Der <xref:System.Runtime.InteropServices>-Namespace stellt drei Kategorien von Interop-spezifischen Attributen zur Verfügung: Attribute, die Sie zur Entwurfszeit anwenden, Attribute, die von COM-Interop-Tools und -APIs während des Konvertierungsprozesses angewendet werden und Attribute, die entweder von Ihnen oder von COM-Interop angewendet werden.  
  
 Wenn Sie mit dem Anwenden von Attributen auf verwalteten Code nicht vertraut sind, finden Sie weitere Informationen unter [Erweitern von Metadaten mithilfe von Attributen](../../../docs/standard/attributes/index.md). Wie andere benutzerdefinierte Attribute können Sie die Interop-spezifischen Attribute auf Typen, Methoden, Eigenschaften, Parameter, Felder und andere Elemente anwenden.  
  
## <a name="design-time-attributes"></a>Entwurfszeitattribute  
 Sie können das Ergebnis des Konvertierungsvorgangs von COM-Interop-Tools und -APIs mithilfe von Entwurfszeitattributen anpassen. Die folgende Tabelle beschreibt die Attribute, die Sie auf dem verwalteten Quellcode anwenden können. COM-Interop-Tools wenden möglicherweise auch die in dieser Tabelle beschriebenen Attribute an.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|<xref:System.Runtime.InteropServices.AutomationProxyAttribute>|Gibt an, ob der Typ mithilfe des Automation-Marshallers oder eines benutzerdefinierten Proxys und Stubs gemarshallt werden soll.|  
|<xref:System.Runtime.InteropServices.ClassInterfaceAttribute>|Steuert den Typ der für eine Klasse generierten Schnittstelle.|  
|<xref:System.Runtime.InteropServices.CoClassAttribute>|Identifiziert den Klassenbezeichner einer aus einer Typbibliothek importierten Co-Klasse.<br /><br /> Dieses Attribut wird in der Regel von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.ComImportAttribute>|Gibt an, dass die Definition einer Co-Klasse oder -Schnittstelle aus einer COM-Typbibliothek importiert wurde. Die Common Language Runtime verwendet dieses Flag, um zu wissen, wie der Typ aktiviert und gemarshallt wird. Dieses Attribut verhindert, dass der Typ zurück in eine Typbibliothek exportiert wird.<br /><br /> Dieses Attribut wird in der Regel von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.ComRegisterFunctionAttribute>|Gibt an, dass eine Methode aufgerufen werden soll, wenn die Assembly für die Verwendung von COM registriert ist, damit der vom Benutzer geschriebene Code während der Registrierung ausgeführt werden kann.|  
|<xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>|Identifiziert Schnittstellen, die Ereignisquellen für die Klasse sind.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.ComUnregisterFunctionAttribute>|Gibt an, dass eine Methode aufgerufen werden soll, wenn die Assembly nicht in COM registriert ist, damit vom Benutzer erstellter Code während des Prozesses ausgeführt werden kann.|  
|<xref:System.Runtime.InteropServices.ComVisibleAttribute>|Macht Typen für COM unsichtbar, wenn der Attributwert **FALSE** ist. Dieses Attribut kann für eine gesamte Assembly oder einen einzelnen Typ angewendet werden, um die COM-Sichtbarkeit zu steuern. Standardmäßig sind alle verwalteten, öffentlichen Typen angezeigt. Das Attribut ist nicht erforderlich, um sie sichtbar zu machen.|  
|<xref:System.Runtime.InteropServices.DispIdAttribute>|Gibt die COM-Dispatch-ID (DISPID) einer Methode oder eines Felds an. Dieses Attribut enthält die DISPID für die Methode, das Feld oder die Eigenschaft, die es beschreibt.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|
|<xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute>|Gibt die Standardschnittstelle für eine in .NET implementierte COM-Klasse an.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|
|<xref:System.Runtime.InteropServices.FieldOffsetAttribute>|Gibt die physische Position jedes Felds innerhalb einer Klasse an, wenn **StructLayoutAttribute** verwendet und **LayoutKind** auf explizit festgelegt ist.|  
|<xref:System.Runtime.InteropServices.GuidAttribute>|Gibt den Globally Unique Identifier (GUID) einer Klasse, Schnittstelle oder einer ganzen Typbibliothek an. Das Format der Zeichenfolge, die an das Attribut übergeben wird, muss ein zulässiges Konstruktorargument für den Typ **System.Guid** darstellen.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute>|Gibt an, welche **IDispatch**-Schnittstellenimplementierung die Common Language Runtime verwendet, wenn sie duale Schnittstellen und Disp-Schnittstellen für COM verfügbar macht.|  
|<xref:System.Runtime.InteropServices.InAttribute>|Gibt an, dass Daten zum Aufrufer gemarshallt werden sollen. Kann zum Zuordnen von Parametern verwendet werden.|  
|<xref:System.Runtime.InteropServices.InterfaceTypeAttribute>|Steuert, wie eine verwaltete Schnittstelle für COM-Clients (Dual, IUnknown-abgeleitet oder nur IDispatch) verfügbar gemacht wird.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.LCIDConversionAttribute>|Gibt an, dass eine nicht verwaltete Methodensignatur einen LCID-Parameter erwartet.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.MarshalAsAttribute>|Gibt an, wie die Daten in Feldern oder Parametern zwischen verwaltetem und nicht verwaltetem Code gemarshallt werden sollen. Das Attribut ist immer optional, da jeder Datentyp standardmäßiges Marshallingverhalten aufweist.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.OptionalAttribute>|Gibt an, dass ein Parameter optional ist.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.OutAttribute>|Gibt an, dass die Daten in einem Feld oder Parameter vom aufgerufenen Objekt zurück an den Aufrufer gemarshallt werden müssen.|  
|<xref:System.Runtime.InteropServices.PreserveSigAttribute>|Unterdrückt das HRESULT oder die Retval-Signaturtransformation, die in der Regel bei Interop-Aufrufen stattfindet. Das Attribut wirkt sich auf Marshalling und das Exportieren der Typbibliothek aus.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|  
|<xref:System.Runtime.InteropServices.ProgIdAttribute>|Gibt die ProgID der .NET Framework-Klasse an. Kann zum Zuordnen von Klassen verwendet werden.|  
|<xref:System.Runtime.InteropServices.StructLayoutAttribute>|Steuert das physische Layout der Felder einer Klasse.<br /><br /> Dieses Attribut wird von COM-Interop-Tools angewendet.|  
  
## <a name="conversion-tool-attributes"></a>Attribute des Konvertierungstools  
 Die folgende Tabelle beschreibt die Attribute, die COM-Interop-Tools während des Konvertierungsvorgangs anwenden. Diese Attribute werden nicht zur Entwurfszeit angewendet.  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|<xref:System.Runtime.InteropServices.ComAliasNameAttribute>|Gibt den COM-Alias für einen Parameter oder Feldtyp an. Kann verwendet werden, um Parameter und Felder zuzuordnen oder Werte zurückzugeben.|  
|<xref:System.Runtime.InteropServices.ComConversionLossAttribute>|Gibt den Informationsverlust zu einer Klasse oder Schnittstelle an, als diese aus einer Typbibliothek in eine Assembly importiert wurden.|  
|<xref:System.Runtime.InteropServices.ComEventInterfaceAttribute>|Identifiziert die Quellschnittstelle und die Klasse, die die Methoden der Ereignisschnittstelle implementieren.|  
|<xref:System.Runtime.InteropServices.ImportedFromTypeLibAttribute>|Gibt an, dass die Assembly ursprünglich aus einer COM-Typbibliothek importiert wurde. Dieses Attribut enthält die Typdefinition für die Bibliothek von der ursprünglichen Typbibliothek.|  
|<xref:System.Runtime.InteropServices.TypeLibFuncAttribute>|Enthält die **FUNCFLAGS**, die ursprünglich für diese Funktion aus der COM-Typbibliothek importiert wurden.|  
|<xref:System.Runtime.InteropServices.TypeLibTypeAttribute>|Enthält die **FUNCFLAGS**, die ursprünglich für diesen Typ aus der COM-Typbibliothek importiert wurden.|  
|<xref:System.Runtime.InteropServices.TypeLibVarAttribute>|Enthält die **FUNCFLAGS**, die ursprünglich für diese Variable aus der COM-Typbibliothek importiert wurden.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices>
- [Verfügbarmachen von .NET Framework-Komponenten in COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [Attribute](../../../docs/standard/attributes/index.md)
- [Qualifizieren von .NET-Typen für die Interoperation](../../../docs/standard/native-interop/qualify-net-types-for-interoperation.md)
- [Verpacken einer .NET Framework-Assembly für COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
