---
title: Veraltete Typen in .NET Framework | Microsoft-Dokumentation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.5, obsolete types
- types, obsolete in .NET Framework 4.5
- obsolete types [.NET Framework]
ms.assetid: e636d024-0fac-45eb-b721-25a8c0ceca8f
caps.latest.revision: 41
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 01c66e2c291766ba00376261740906934f065855
ms.openlocfilehash: b7040d4c82c9434b2d24a579a93602660479ec59
ms.contentlocale: de-de
ms.lasthandoff: 05/22/2017

---
# Veraltete Typen in .NET Framework
<a id="obsolete-types-in-the-net-framework" class="xliff"></a>
<a name="introduction"></a> In den Tabellen dieses Artikels sind die Typen aufgeführt, die in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] und [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] veraltet sind, geordnet nach Assembly. Über die nachfolgenden Links finden Sie eine Liste der veralteten Typen und empfohlenen Alternativen in den jeweiligen Assemblys. Da diese Typen veraltet sind, sind alle ihrer Member ebenfalls veraltet. Eine Liste weiterer veralteter Member in der .NET Framework-Klassenbibliothek finden Sie unter [Veraltete Member](../../../docs/framework/whats-new/obsolete-members.md).  
  
-   [Veraltete Typen in Systemassemblys](#obsolete_types_in_system_assemblies)  
  
    -   [mscorlib.dll](#mscorlib)  
  
    -   [System.Core.dll](#Core)  
  
    -   [System.Data.dll](#data)  
  
    -   [System.Data.OracleClient.dll](#oracleclient)  
  
    -   [System.Design.dll](#design)  
  
    -   [System.dll](#system)  
  
    -   [System.EnterpriseServices.dll](#enterpriseservices)  
  
    -   [System.Net.dll](#net)  
  
    -   [System.ServiceModel.dll](#servicemodel)  
  
    -   [System.Web.dll](#web)  
  
    -   [System.Web.Mobile.dll](#mobile)  
  
    -   [System.Workflow.Activities.dll](#workflow_activities)  
  
    -   [System.Workflow.ComponentModel.dll](#workflow_componentmodel)  
  
    -   [System.Workflow.Runtime.dll](#workflow_runtime)  
  
    -   [System.WorkflowServices.dll](#workflowservices)  
  
    -   [System.Xaml.dll](#xaml)  
  
    -   [System.Xml.dll](#xml)  
  
    -   [WindowsBase.dll](#WindowsBase)  
  
-   [Veraltete Typen in Microsoft-Assemblys](#obsolete_types_in_microsoft_assemblies)  
  
    -   [IEHost.dll und IEExec.exe](#IEHost)  
  
    -   [Microsoft.Build.Engine.dll](#Engine)  
  
    -   [Microsoft.JScript.dll](#jscript)  
  
    -   [Microsoft.VisualBasic.Compatibility.dll](#VBCompat)  
  
    -   [Microsoft.VisualBasic.Compatibility.Data.dll](#VBCompatData)  
  
    -   [Microsoft.VisualC.dll](#visualc)  
  
<a name="obsolete_types_in_system_assemblies"></a>   
## Veraltete Typen in Systemassemblys
<a id="obsolete-types-in-system-assemblies" class="xliff"></a>  
 In den folgenden Tabellen sind die Typen aufgeführt, die in Systemassemblys als veraltet eingestuft wurden. Diese Assemblys werden zur allgemeinen Anwendungsentwicklung für .NET Framework verwendet.  
  
<a name="mscorlib"></a>   
### Assembly: mscorlib.dll
<a id="assembly-mscorlibdll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.ExecutionEngineException?displayProperty=fullName>|Dieser Typ hat bisher einen nicht näher beschriebenen schwerwiegenden Fehler angegeben. Die Laufzeit löst diese Ausnahme nicht mehr aus, sodass dieser Typ veraltet ist.|  
|<xref:System.Collections.CaseInsensitiveHashCodeProvider?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.StringComparer?displayProperty=fullName>.|  
|<xref:System.Collections.IHashCodeProvider?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Collections.IEqualityComparer?displayProperty=fullName>.|  
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=fullName>|Die <xref:System.Configuration.Assemblies.AssemblyHash>-Klasse ist veraltet.|  
|<xref:System.Diagnostics.Contracts.Internal.ContractHelper?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5. Verwenden Sie stattdessen die <xref:System.Runtime.CompilerServices.ContractHelper?displayProperty=fullName>-Klasse im System.Runtime.CompilerServices-Namespace.|  
|<xref:System.Reflection.Emit.UnmanagedMarshal?displayProperty=fullName>|Es steht eine alternative API zur Verfügung: Geben Sie stattdessen das benutzerdefinierte <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName>-Attribut aus.|  
|<xref:System.Runtime.InteropServices.BIND_OPTS?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.BIND_OPTS?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.BINDPTR?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.BINDPTR?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.CALLCONV?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.CALLCONV?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.CONNECTDATA?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.CONNECTDATA?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.DESCKIND?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.DESCKIND?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.DISPPARAMS?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.DISPPARAMS?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.ELEMDESC?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.ELEMDESC?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.EXCEPINFO?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.EXCEPINFO?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.FILETIME?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.FILETIME?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.FUNCDESC?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.FUNCDESC?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.FUNCFLAGS?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.FUNCFLAGS?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.FUNCKIND?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.FUNCKIND?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=fullName>|Dieses Attribut ist veraltet und wird in einer der nächsten Versionen entfernt.|  
|<xref:System.Runtime.InteropServices.IDispatchImplType?displayProperty=fullName>|Das <xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=fullName>-Objekt ist veraltet.|  
|<xref:System.Runtime.InteropServices.IDLDESC?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IDLDESC?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.IDLFLAG?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IDLFLAG?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.IMPLTYPEFLAGS?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IMPLTYPEFLAGS?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.INVOKEKIND?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.INVOKEKIND?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.LIBFLAGS?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.LIBFLAGS?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.PARAMDESC?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.PARAMDESC?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.PARAMFLAG?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.PARAMFLAG?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.SetWin32ContextInIDispatchAttribute?displayProperty=fullName>|Dieses Attribut ist veraltet. Anwendungsdomänen beachten Aktivierungskontextgrenzen in IDispatch-Aufrufen nicht mehr.|  
|<xref:System.Runtime.InteropServices.STATSTG?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.STATSTG?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.SYSKIND?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.SYSKIND?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.TYPEATTR?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPEATTR?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.TYPEDESC?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPEDESC?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.TYPEFLAGS?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPEFLAGS?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.TYPEKIND?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPEKIND?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.TYPELIBATTR?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPELIBATTR?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIBindCtx?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IBindCtx?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIConnectionPoint?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIConnectionPointContainer?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIEnumConnectionPoints?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumConnectionPoints?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIEnumConnections?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumConnections?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIEnumMoniker?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumMoniker?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIEnumString?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumString?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIEnumVARIANT?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIMoniker?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IMoniker?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIPersistFile?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IPersistFile?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIRunningObjectTable?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IRunningObjectTable?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMIStream?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMITypeComp?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.ITypeComp?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMITypeInfo?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.UCOMITypeLib?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.ITypeLib?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.VARDESC?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.VARDESC?displayProperty=fullName> .|  
|<xref:System.Runtime.InteropServices.VARFLAGS?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.VARFLAGS?displayProperty=fullName> .|  
|<xref:System.Security.SecurityCriticalScope?displayProperty=fullName>|<xref:System.Security.SecurityCriticalScope> wird nur für .NET 2.0-Transparenzkompatibilität verwendet.|  
|<xref:System.Security.SecurityTreatAsSafeAttribute?displayProperty=fullName>|<xref:System.Security.SecurityTreatAsSafeAttribute> wird nur für .NET 2.0-Transparenzkompatibilität verwendet. Verwenden Sie stattdessen <xref:System.Security.SecuritySafeCriticalAttribute?displayProperty=fullName>.|  
|<xref:System.Security.Policy.FirstMatchCodeGroup?displayProperty=fullName>|Dieser Typ ist veraltet und wird in einem der nächsten Releases von .NET Framework entfernt.|  
|<xref:System.Security.Policy.PermissionRequestEvidence?displayProperty=fullName>|Die Deklarationssicherheit auf Assemblyebene wurde als veraltet eingestuft und wird von der CLR nicht mehr als Standardeinstellung erzwungen.|  
|<xref:System.Security.Policy.UnionCodeGroup?displayProperty=fullName>|Dieser Typ ist veraltet und wird in einem der nächsten Releases von .NET Framework entfernt.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="Core"></a>   
### Assembly: System.Core.dll
<a id="assembly-systemcoredll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.Runtime.CompilerServices.ExecutionScope?displayProperty=fullName>|Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Verwenden Sie diesen Typ nicht.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="data"></a>   
### Assembly: System.Data.dll
<a id="assembly-systemdatadll" class="xliff"></a>  
  
|Typ|Nachricht|  
|----------|-------------|  
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=fullName>|<xref:System.Data.DataSysDescriptionAttribute> ist veraltet.|  
|<xref:System.Data.PropertyAttributes?displayProperty=fullName>|<xref:System.Data.PropertyAttributes> ist veraltet.|  
|<xref:System.Data.TypedDataSetGenerator?displayProperty=fullName>|Die <xref:System.Data.TypedDataSetGenerator>-Klasse wird in einer der nächsten Versionen entfernt. Verwenden Sie <xref:System.Data.Design.TypedDataSetGenerator?displayProperty=fullName> in "System.Design.dll".|  
|<xref:System.Xml.XmlDataDocument?displayProperty=fullName>|Die <xref:System.Xml.XmlDataDocument>-Klasse wird in einer der nächsten Versionen entfernt.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="oracleclient"></a>   
### Assembly: System.Data.OracleClient.dll
<a id="assembly-systemdataoracleclientdll" class="xliff"></a>  
  
|Typ|Nachricht|  
|----------|-------------|  
|<xref:System.Data.OracleClient.OracleClientFactory?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleClientFactory> ist veraltet.|  
|<xref:System.Data.OracleClient.OracleCommand?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleCommand> ist veraltet.|  
|<xref:System.Data.OracleClient.OracleCommandBuilder?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleCommandBuilder> ist veraltet.|  
|<xref:System.Data.OracleClient.OracleConnection?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleConnection> ist veraltet.|  
|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder> ist veraltet.|  
|<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=fullName>|<xref:System.Data.OracleClient.OracleDataAdapter> ist veraltet.|  
|<xref:System.Data.OracleClient.OraclePermission?displayProperty=fullName>|<xref:System.Data.OracleClient.OraclePermission> ist veraltet.|  
|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName>|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=fullName> ist veraltet.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="design"></a>   
### Assembly: System.Design.dll
<a id="assembly-systemdesigndll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.ComponentModel.Design.LocalizationExtenderProvider?displayProperty=fullName>|Diese Klasse ist veraltet. Verwenden Sie stattdessen <xref:System.ComponentModel.Design.Serialization.CodeDomLocalizationProvider?displayProperty=fullName> .|  
|<xref:System.Web.UI.Design.DataBindingCollectionConverter?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da die Bearbeitung von Datenbindungen über <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=fullName> gestartet wird, anstatt über das Eigenschaftenraster.|  
|<xref:System.Web.UI.Design.DataBindingCollectionEditor?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da die Bearbeitung von Datenbindungen über <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=fullName> gestartet wird, anstatt über das Eigenschaftenraster.|  
|<xref:System.Web.UI.Design.IControlDesignerBehavior?displayProperty=fullName>|Die empfohlenen Alternativen sind <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=fullName> und <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.IHtmlControlDesignerBehavior?displayProperty=fullName>|Die empfohlenen Alternativen sind <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=fullName> und <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=fullName>.|  
|<xref:System.Web.UI.Design.ITemplateEditingFrame?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da die Vorlagenbearbeitung in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> behandelt wird. Machen Sie zum Unterstützen der Vorlagenbearbeitung die Vorlagendaten in der <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName>-Eigenschaft verfügbar, und rufen Sie <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName> auf.|  
|<xref:System.Web.UI.Design.IWebFormReferenceManager?displayProperty=fullName>|Die empfohlene Alternative ist <xref:System.Web.UI.Design.WebFormsReferenceManager?displayProperty=fullName>. Das <xref:System.Web.UI.Design.WebFormsReferenceManager>-Objekt enthält zusätzliche Funktionalität und ermöglicht eine stärkere Erweiterbarkeit. Verwenden Sie die <xref:System.Web.UI.Design.WebFormsReferenceManager>-Eigenschaft des `RootDesigner.ReferenceManager`-Objekts, um das <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>-Objekt abzurufen.|  
|<xref:System.Web.UI.Design.IWebFormsDocumentService?displayProperty=fullName>|Die empfohlene Alternative ist <xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=fullName>. Das <xref:System.Web.UI.Design.WebFormsRootDesigner>-Objekt enthält zusätzliche Funktionalität und ermöglicht eine stärkere Erweiterbarkeit. Verwenden Sie die <xref:System.Web.UI.Design.WebFormsRootDesigner>-Eigenschaft des <xref:System.Web.UI.Design.ControlDesigner.RootDesigner%2A>-Objekts, um das <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName>-Objekt abzurufen.|  
|<xref:System.Web.UI.Design.ITemplateEditingService?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da die Vorlagenbearbeitung in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> behandelt wird. Machen Sie zum Unterstützen der Vorlagenbearbeitung die Vorlagendaten in der <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName>-Eigenschaft verfügbar, und rufen Sie <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName> auf.|  
|<xref:System.Web.UI.Design.ReadWriteControlDesigner?displayProperty=fullName>|Die empfohlene Alternative ist das <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=fullName>-Objekt, da es ein <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=fullName>-Objekt zum Bearbeiten des Inhalts verwendet. Designerbereiche ermöglichen eine bessere Steuerung des zu bearbeitenden Inhalts.|  
|<xref:System.Web.UI.Design.TemplateEditingService?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da die Vorlagenbearbeitung in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> behandelt wird. Machen Sie zum Unterstützen der Vorlagenbearbeitung die Vorlagendaten in der <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName>-Eigenschaft verfügbar, und rufen Sie <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName> auf.|  
|<xref:System.Web.UI.Design.TemplateEditingVerb?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da die Vorlagenbearbeitung in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> behandelt wird. Machen Sie zum Unterstützen der Vorlagenbearbeitung die Vorlagendaten in der <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=fullName>-Eigenschaft verfügbar, und rufen Sie <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=fullName> auf.|  
|<xref:System.Web.UI.Design.WebControls.CalendarAutoFormatDialog?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da das Dialogfeld "AutoFormat" vom Designerhost gestartet wird. Die Liste der verfügbaren automatischen Formatierungen wird für <xref:System.Web.UI.Design.ControlDesigner?displayProperty=fullName> in der <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=fullName>-Eigenschaft verfügbar gemacht.|  
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=fullName>|Die empfohlene Alternative ist das <xref:System.Web.UI.Design.WebControls.PanelContainerDesigner?displayProperty=fullName>-Objekt, da es ein <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=fullName>-Objekt zum Bearbeiten des Inhalts verwendet. Designerbereiche ermöglichen eine bessere Steuerung des zu bearbeitenden Inhalts.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="system"></a>   
### Assembly: System.dll
<a id="assembly-systemdll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.ComponentModel.IComNativeDescriptorHandler?displayProperty=fullName>|Diese Schnittstelle ist veraltet. Fügen Sie stattdessen einen <xref:System.ComponentModel.TypeDescriptionProvider?displayProperty=fullName> hinzu, um den Typ <xref:System.ComponentModel.TypeDescriptor.ComObjectType%2A?displayProperty=fullName> zu behandeln.|  
|<xref:System.ComponentModel.RecommendedAsConfigurableAttribute?displayProperty=fullName>|Verwenden Sie stattdessen <xref:System.ComponentModel.SettingsBindableAttribute?displayProperty=fullName>, um mit dem neuen Einstellungsmodell zu arbeiten.|  
|<xref:System.ComponentModel.Design.Serialization.RootDesignerSerializerAttribute?displayProperty=fullName>|Dieses Attribut ist veraltet. Verwenden Sie stattdessen <xref:System.ComponentModel.Design.Serialization.DesignerSerializerAttribute?displayProperty=fullName>. Verwenden Sie zum Angeben eines Stamm-Designers für CodeDom beispielsweise `DesignerSerializerAttribute\(...,typeof\(TypeCodeDomSerializer\)\)`.|  
|<xref:System.Diagnostics.DiagnosticsConfigurationHandler?displayProperty=fullName>|Diese Klasse ist veraltet.|  
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=fullName>|Diese Klasse ist veraltet. Verwenden Sie stattdessen die Leistungsindikatoren über die <xref:System.Diagnostics.PerformanceCounter?displayProperty=fullName>-Klasse.|  
|<xref:System.Net.GlobalProxySelection?displayProperty=fullName>|Diese Klasse ist veraltet. Verwenden Sie stattdessen <xref:System.Net.WebRequest.DefaultWebProxy%2A?displayProperty=fullName>, um auf den globalen Standardproxy zuzugreifen und diesen festzulegen. Verwenden Sie "null" anstelle von <xref:System.Net.GlobalProxySelection.GetEmptyWebProxy%2A?displayProperty=fullName>.|  
|<xref:System.Net.Sockets.SocketClientAccessPolicyProtocol?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung aus dem Code vorgesehen.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="enterpriseservices"></a>   
### Assembly: System.EnterpriseServices.dll
<a id="assembly-systementerpriseservicesdll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.EnterpriseServices.RegistrationHelperTx?displayProperty=fullName>|Die <xref:System.EnterpriseServices.RegistrationHelperTx>-Klasse ist veraltet.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="net"></a>   
### Assembly: System.Net.dll
<a id="assembly-systemnetdll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.Net.INetworkProgress?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Net.IUnsafeWebRequestCreate?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Net.NetworkProgressChangedEventArgs?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Net.UiSynchronizationContext?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Net.Sockets.HttpPolicyDownloaderProtocol?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Net.Sockets.SecurityCriticalAction?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Net.Sockets.SocketPolicy?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Net.Sockets.UdpAnySourceMulticastClient?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Net.Sockets.UdpSingleSourceMulticastClient?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung aus dem Code vorgesehen.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="servicemodel"></a>   
### Assembly: System.ServiceModel.dll
<a id="assembly-systemservicemodeldll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.ServiceModel.NetPeerTcpBinding?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|  
|<xref:System.ServiceModel.Channels.HttpCookieContainerBindingElement?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Dieser Typ ist veraltet. Um HTTP <xref:System.Net.CookieContainer> zu aktivieren, verwenden Sie die `AllowCookies`-Eigenschaft auf der HTTP-Bindung oder auf <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.|  
|<xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|  
|<xref:System.ServiceModel.Channels.PeerTransportBindingElement?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|  
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingCollectionElement?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|  
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|  
|<xref:System.ServiceModel.Configuration.PeerTransportElement?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|  
|<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="web"></a>   
### Assembly: System.Web.dll
<a id="assembly-systemwebdll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.Web.Configuration.PassportAuthentication?displayProperty=fullName>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](http://go.microsoft.com/fwlink/?LinkId=733413) abgelöst.|  
|<xref:System.Web.Mail.MailAttachment?displayProperty=fullName>|Die empfohlene Alternative ist <xref:System.Net.Mail.Attachment?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailEncoding?displayProperty=fullName>|Die empfohlene Alternative ist <xref:System.Net.Mime.TransferEncoding?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailFormat?displayProperty=fullName>|Die empfohlene Alternative ist <xref:System.Net.Mail.MailMessage.IsBodyHtml%2A?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailMessage?displayProperty=fullName>|Die empfohlene Alternative ist <xref:System.Net.Mail.MailMessage?displayProperty=fullName>.|  
|<xref:System.Web.Mail.MailPriority?displayProperty=fullName>|Die empfohlene Alternative ist <xref:System.Net.Mail.MailPriority?displayProperty=fullName>.|  
|<xref:System.Web.Mail.SmtpMail?displayProperty=fullName>|Die empfohlene Alternative ist <xref:System.Net.Mail.SmtpClient?displayProperty=fullName>.|  
|<xref:System.Web.Security.PassportAuthenticationEventArgs?displayProperty=fullName>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](http://go.microsoft.com/fwlink/?LinkId=733413) abgelöst.|  
|<xref:System.Web.Security.PassportAuthenticationEventHandler?displayProperty=fullName>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](http://go.microsoft.com/fwlink/?LinkId=733413) abgelöst.|  
|<xref:System.Web.Security.PassportAuthenticationModule?displayProperty=fullName>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](http://go.microsoft.com/fwlink/?LinkId=733413) abgelöst.|  
|<xref:System.Web.Security.PassportIdentity?displayProperty=fullName>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](http://go.microsoft.com/fwlink/?LinkId=733413) abgelöst.|  
|<xref:System.Web.Security.PassportPrincipal?displayProperty=fullName>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](http://go.microsoft.com/fwlink/?LinkId=733413) abgelöst.|  
|<xref:System.Web.UI.ObjectConverter?displayProperty=fullName>|Die empfohlenen Alternativen sind <xref:System.Convert?displayProperty=fullName> und <xref:System.String.Format%2A?displayProperty=fullName>.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="mobile"></a>   
### Assembly: System.Web.Mobile.dll
<a id="assembly-systemwebmobiledll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.Web.Mobile.CookielessData?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFilterElement?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFilterElementCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.DeviceFiltersSection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.ErrorHandlerModule?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileCapabilities?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileDeviceCapabilitiesSectionHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileErrorInfo?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.Mobile.MobileFormsAuthentication?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.IMobileDesigner?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.IMobileWebFormServices?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.MobileResource?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.Converters.DataFieldConverter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.Design.MobileControls.Converters.DataMemberConverter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.AdRotator?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Alignment?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ArrayListCollectionBase?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.BaseValidator?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.BooleanOption?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Calendar?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Command?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CommandFormat?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CompareValidator?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Constants?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlElement?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlElementCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ControlPager?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.CustomValidator?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DesignerAdapterAttribute?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceElement?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceElementCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceOverridableAttribute?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecific?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoice?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateContainer?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.DeviceSpecificControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ErrorFormatterPage?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FontInfo?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FontSize?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Form?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FormControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.FormMethod?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IControlAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Image?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IObjectListFieldCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.IPageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ItemPager?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ITemplateable?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Label?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Link?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.List?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListCommandEventArgs?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListCommandEventHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDataBindEventArgs?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDataBindEventHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListDecoration?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ListSelectType?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralLink?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralText?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralTextContainerControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LiteralTextControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LoadItemsEventArgs?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.LoadItemsEventHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControl?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlsSection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileControlsSectionHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItem?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItemCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileListItemType?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobilePage?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileTypeNameConverter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.MobileUserControl?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectList?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommand?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventArgs?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventArgs?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListField?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListFieldCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListItem?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListItemCollection?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventArgs?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventArgs?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListTitleAttribute?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ObjectListViewMode?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PagedControl?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PagerStyle?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Panel?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PanelControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PersistNameAttribute?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.PhoneCall?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RangeValidator?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RegularExpressionValidator?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.RequiredFieldValidator?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.SelectionList?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Style?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.StyleSheet?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.StyleSheetControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TemplateContainer?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextBox?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextBoxControlBuilder?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextControl?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextView?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.TextViewElement?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.ValidationSummary?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Wrapping?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCalendarAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCommandAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlFormAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlImageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlLinkAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlMobileTextWriter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPhoneCallAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlSelectionListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlTextBoxAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.ControlAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCalendarAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCommandAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlControlAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlFormAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlImageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLabelAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLinkAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLiteralTextAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlMobileTextWriter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlObjectListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPanelAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPhoneCallAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlSelectionListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextBoxAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextViewAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidationSummaryAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidatorAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.MobileTextWriter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.MultiPartWriter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlMobileTextWriter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlPageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlCalendarAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlCommandAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlControlAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlFormAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlImageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLabelAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLinkAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlLiteralTextAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlMobileTextWriter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlObjectListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPanelAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPhoneCallAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlPostFieldType?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlSelectionListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextBoxAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextViewAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidationSummaryAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidatorAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.Doctype?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.StyleSheetLocation?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCalendarAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCommandAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlControlAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCssHandler?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlFormAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlImageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLabelAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLinkAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLiteralTextAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlMobileTextWriter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlObjectListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPageAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPanelAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPhoneCallAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlSelectionListAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextBoxAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextViewAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidationSummaryAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidatorAdapter?displayProperty=fullName>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](http://go.microsoft.com/fwlink/?LinkId=157231).|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="workflow_activities"></a>   
### Assembly: System.Workflow.Activities.dll
<a id="assembly-systemworkflowactivitiesdll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|Alle Typen im <xref:System.Workflow.Activities?displayProperty=fullName>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Configuration.ActiveDirectoryRoleFactoryConfiguration?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleActionTrackingEvent?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleConditionReference?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Activities.Rules.RuleSetReference?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="workflow_componentmodel"></a>   
### Assembly: System.Workflow.ComponentModel.dll
<a id="assembly-systemworkflowcomponentmodeldll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|Alle Typen im <xref:System.Workflow.ComponentModel>-Namespace außer <xref:System.Workflow.ComponentModel.GetValueOverride?displayProperty=fullName> und <xref:System.Workflow.ComponentModel.SetValueOverride?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|Alle Typen im <xref:System.Workflow.ComponentModel.Compiler>-Namespace außer <xref:System.Workflow.ComponentModel.Compiler.ValidationError?displayProperty=fullName> und <xref:System.Workflow.ComponentModel.Compiler.ValidationErrorCollection?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|Alle Typen im <xref:System.Workflow.ComponentModel.Design>-Namespace außer <xref:System.Workflow.ComponentModel.Design.ConnectorEventHandler>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializationManager?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializer?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityMarkupSerializer?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivitySurrogateSelector?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.ActivityTypeCodeDomSerializer?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.CompositeActivityMarkupSerializer?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.ComponentModel.Serialization.DependencyObjectCodeDomSerializer?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="workflow_runtime"></a>   
### Assembly: System.Workflow.Runtime.dll
<a id="assembly-systemworkflowruntimedll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------| 
|<xref:System.Activities.Statements.Interop>|Zuerst veraltet in .NET Framework 4.5.<br /><br />Die Workflow Foundation 3.0-Typen sind veraltet. Verwenden Sie stattdessen die Workflow 4.0-Typen von <xref:System.Activities>.\*.|  
|<xref:System.Activities.Tracking.InteropTrackingRecord>|Zuerst veraltet in .NET Framework 4.5.<br /><br />Die Workflow Foundation 3.0-Typen sind veraltet. Verwenden Sie stattdessen die Workflow 4.0-Typen von <xref:System.Activities>.\*.|   
|Alle Typen im <xref:System.Workflow.Runtime>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|Alle Typen im <xref:System.Workflow.Runtime.Configuration>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|Alle Typen im <xref:System.Workflow.Runtime.DebugEngine>-Namespace außer <xref:System.Workflow.Runtime.DebugEngine.DebugEngineCallback>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|Alle Typen im <xref:System.Workflow.Runtime.Hosting>-Namespace außer <xref:System.Workflow.Runtime.Hosting.WorkflowCommitWorkBatchService.CommitWorkBatchCallback>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
|Alle Typen im <xref:System.Workflow.Runtime.Tracking>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\* Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>.\*.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="workflowservices"></a>   
### Assembly: System.WorkflowServices.dll
<a id="assembly-systemworkflowservicesdll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.ServiceModel.WorkflowServiceHost?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Activation.WorkflowServiceHostFactory?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Activities.Description.WorkflowRuntimeEndpoint?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.ExtendedWorkflowRuntimeServiceElementCollection?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.PersistenceProviderElement?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Configuration.WorkflowRuntimeElement?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.DurableOperationAttribute?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.DurableServiceAttribute?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.PersistenceProviderBehavior?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.UnknownExceptionAction?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Description.WorkflowRuntimeBehavior?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Dispatcher.DurableOperationContext?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.InstanceLockException?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.InstanceNotFoundException?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.LockingPersistenceProvider?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceException?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceProvider?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.PersistenceProviderFactory?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.ServiceModel.Persistence.SqlPersistenceProviderFactory?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|Alle Typen im <xref:System.Workflow.Activities?displayProperty=fullName>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
|<xref:System.Workflow.Runtime.Hosting.ChannelManagerService?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>.\*.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="xaml"></a>   
### Assembly: System.Xaml.dll
<a id="assembly-systemxamldll" class="xliff"></a>  
  
|Typ|Nachricht|  
|----------|-------------|  
|<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute?displayProperty=fullName>|Wird vom XAML-Parser nicht verwendet. Sehen Sie unter <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=fullName> nach.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="xml"></a>   
### Assembly: System.Xml.dll
<a id="assembly-systemxmldll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:System.Xml.IApplicationResourceStreamResolver?displayProperty=fullName>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung aus dem Code vorgesehen.|  
|<xref:System.Xml.Schema.XmlSchemaCollection?displayProperty=fullName>|Verwenden Sie <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=fullName> für die Schemakompilierung und -validierung.|  
|<xref:System.Xml.XmlValidatingReader?displayProperty=fullName>|Verwenden Sie stattdessen ein <xref:System.Xml.XmlReader?displayProperty=fullName>-Objekt, das von der <xref:System.Xml.XmlReader.Create%2A?displayProperty=fullName>-Methode erstellt wird, mit dem entsprechenden <xref:System.Xml.XmlReaderSettings?displayProperty=fullName>-Objekt.|  
|<xref:System.Xml.XmlXapResolver?displayProperty=fullName>|Die Verwendung dieses Typs generiert einen Compilerfehler. Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|  
|<xref:System.Xml.Xsl.XslTransform?displayProperty=fullName>|Diese Klasse ist veraltet. Verwenden Sie stattdessen <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=fullName>.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="WindowsBase"></a>   
### Assembly: WindowsBase.dll
<a id="assembly-windowsbasedll" class="xliff"></a>  
  
|Typ|Nachricht|  
|----------|-------------|  
|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=fullName>|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=fullName> ist veraltet. Diese Schnittstelle wird nicht mehr verwendet.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="obsolete_types_in_microsoft_assemblies"></a>   
## Veraltete Typen in Microsoft-Assemblys
<a id="obsolete-types-in-microsoft-assemblies" class="xliff"></a>  
 In den folgenden Abschnitten sind die veralteten Typen in Microsoft-Assemblys aufgeführt. Bei diesen Assemblys handelt es sich um zweckgebundene Assemblys, beispielsweise Assemblys, die auf eine einzelne Sprache abzielen (z. B. Microsoft.JScript.dll oder Microsoft.VisualC.dll).  
  
<a name="IEHost"></a>   
### Assembly: IEHost.dll und IEExec.exe
<a id="assembly-iehostdll-and-ieexecexe" class="xliff"></a>  
 Die IEHost.dll-Assembly und die IEExec.exe-Assembly wurden aus .NET Framework entfernt. Alle ihrer Typen und Member sind veraltet und werden ab [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] nicht mehr unterstützt. Diese Assemblys wurden verwendet, um Windows Forms-Steuerelemente zu hosten und ausführbare Dateien in Internet Explorer auszuführen. Empfohlene Alternativen schließen ClickOnce, XAML-Browseranwendungen (XBAP) und Microsoft Silverlight ein.  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="Engine"></a>   
### Assembly: Microsoft.Build.Engine.dll
<a id="assembly-microsoftbuildenginedll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=fullName>|Diese Klasse ist veraltet. Verwenden Sie stattdessen bitte <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName> aus der *Microsoft.Build*-Assembly.|  
|<xref:Microsoft.Build.BuildEngine.Project?displayProperty=fullName>|Diese Klasse ist veraltet. Verwenden Sie stattdessen bitte <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=fullName> aus der *Microsoft.Build*-Assembly.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="jscript"></a>   
### Assembly: Microsoft.JScript.dll
<a id="assembly-microsoftjscriptdll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:Microsoft.JScript.Vsa.BaseVsaEngine?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.BaseVsaSite?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.BaseVsaStartup?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaCodeItem?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaEngine?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaError?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaGlobalItem?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaItem?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaItems?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaPersistSite?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaReferenceItem?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.IJSVsaSite?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.JSVsaError?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.JSVsaException?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.JSVsaItemFlag?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.JSVsaItemType?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.ResInfo?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
|<xref:Microsoft.JScript.Vsa.VsaEngine?displayProperty=fullName>|Die Verwendung dieses Typs wird nicht empfohlen, da er in Visual Studio 2005 als veraltet eingestuft ist. Für diese Funktion wird kein Ersatz bereitgestellt. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=fullName>.|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="VBCompat"></a>   
### Assembly: Microsoft.VisualBasic.Compatibility.dll
<a id="assembly-microsoftvisualbasiccompatibilitydll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseControlArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseOcxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ButtonArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckedListBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ColorDialogArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ComboBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBox?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBox?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBox?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FixedLengthString?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FontDialogArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FormShowConstants?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.GroupBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.HScrollBarArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ImageListArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LabelArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxItem?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListViewArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LoadResConstants?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MaskedTextBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MenuItemArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MouseButtonConstants?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.OpenFileDialogArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PanelArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PictureBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PrintDialogArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ProgressBarArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RadioButtonArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RichTextBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SaveFileDialogArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ScaleMode?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ShiftConstants?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusBarArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusStripArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.Support?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TabControlArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TextBoxArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TimerArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolBarArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripMenuItemArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TreeViewArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.VScrollBarArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebBrowserArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClass?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassContainingClassNotOptional?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassCouldNotFindEvent?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemCannotBeCurrentWebItem?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemRespondNotFound?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassUserWebClassNameNotOptional?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebClassFileNameNotOptional?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebItemNotValid?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItem?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemAssociatedWebClassNotOptional?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemClosingTagNotFound?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadEmbeddedResource?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadTemplateFile?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNameNotOptional?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNoTemplateSpecified?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemTooManyNestedTags?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemUnexpectedErrorReadingTemplateFile?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ZOrderConstants?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="VBCompatData"></a>   
### Assembly: Microsoft.VisualBasic.Compatibility.Data.dll
<a id="assembly-microsoftvisualbasiccompatibilitydatadll" class="xliff"></a>  
  
|Typ|Meldung|  
|----------|-------------|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.BOFActionEnum?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EndOfRecordsetDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EOFActionEnum?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.ErrorDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchCompleteDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchProgressDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FieldChangeCompleteDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.MoveCompleteDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.OrientationEnum?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordChangeCompleteDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordsetChangeCompleteDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeFieldDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordsetDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillMoveDelegate?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODCArray?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseDataEnvironment?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BindingCollectionEnumerator?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CONNECTDATA?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBBINDING?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBCOLUMNINFO?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBID?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBinding?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBindingCollection?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBKINDENUM?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBPROPIDSET?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IAccessor?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IChapteredRowset?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IColumnsInfo?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPoint?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPointContainer?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormat?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormatDisp?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnectionPoints?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnections?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPosition?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPositionChange?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowset?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetChange?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetIdentity?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetInfo?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetNotify?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBinding?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBindingCollection?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SRDescriptionAttribute?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UGUID?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UNAME?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UpdateMode?displayProperty=fullName>|Siehe [Microsoft.VisualBasic.Compatibility.VB6.\<Member> ist veraltet und wird nur in 32-Bit-Prozessen unterstützt](https://msdn.microsoft.com/library/ee839621.aspx).|  
  
 [Zurück zum Anfang](#introduction)  
  
<a name="visualc"></a>   
### Assembly: Microsoft.VisualC.dll
<a id="assembly-microsoftvisualcdll" class="xliff"></a>  
  
|Typ|Nachricht|  
|----------|-------------|  
|<xref:Microsoft.VisualC.DebugInfoInPDBAttribute?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.DecoratedNameAttribute?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.IsConstModifier?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.IsCXXReferenceModifier?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.IsLongModifier?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.IsSignedModifier?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.IsVolatileModifier?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.MiscellaneousBitsAttribute?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.NeedsCopyConstructorModifier?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
|<xref:Microsoft.VisualC.NoSignSpecifiedModifier?displayProperty=fullName>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|  
  
## Siehe auch
<a id="see-also" class="xliff"></a>  
 [Veraltete Elemente in der Klassenbibliothek](../../../docs/framework/whats-new/whats-obsolete.md)   
 [Veraltete Member](../../../docs/framework/whats-new/obsolete-members.md)

