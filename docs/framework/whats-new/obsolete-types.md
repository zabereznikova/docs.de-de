---
title: Veraltete Typen in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, obsolete types
- types, obsolete in .NET Framework 4.5
- obsolete types [.NET Framework]
ms.assetid: e636d024-0fac-45eb-b721-25a8c0ceca8f
ms.openlocfilehash: b7932a553f39e1f1da2a3946878d6224099da8da
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802686"
---
# <a name="obsolete-types-in-the-net-framework"></a>Veraltete Typen in .NET Framework

<a name="introduction"></a> In den Tabellen in diesem Artikel werden die Typen aufgeführt, die in .NET Framework 4.5 und .NET Framework 4.6 veraltet sind (sortiert nach Assembly). Über die nachfolgenden Links finden Sie eine Liste der veralteten Typen und empfohlenen Alternativen in den jeweiligen Assemblys. Da diese Typen veraltet sind, sind alle ihrer Member ebenfalls veraltet. Eine Liste weiterer veralteter Member in der .NET Framework-Klassenbibliothek finden Sie unter [Veraltete Member](obsolete-members.md).

- [Veraltete Typen in Systemassemblys](#obsolete_types_in_system_assemblies)

  - [mscorlib.dll](#mscorlib)

  - [System.Core.dll](#Core)

  - [System.Data.dll](#data)

  - [System.Data.OracleClient.dll](#oracleclient)

  - [System.Design.dll](#design)

  - [System.dll](#system)

  - [System.EnterpriseServices.dll](#enterpriseservices)

  - [System.Net.dll](#net)

  - [System.ServiceModel.dll](#servicemodel)

  - [System.Web.dll](#web)

  - [System.Web.Mobile.dll](#mobile)

  - [System.Workflow.Activities.dll](#workflow_activities)

  - [System.Workflow.ComponentModel.dll](#workflow_componentmodel)

  - [System.Workflow.Runtime.dll](#workflow_runtime)

  - [System.WorkflowServices.dll](#workflowservices)

  - [System.Xaml.dll](#xaml)

  - [System.Xml.dll](#xml)

  - [WindowsBase.dll](#WindowsBase)

- [Veraltete Typen in Microsoft-Assemblys](#obsolete_types_in_microsoft_assemblies)

  - [IEHost.dll und IEExec.exe](#IEHost)

  - [Microsoft.Build.Engine.dll](#Engine)

  - [Microsoft.JScript.dll](#jscript)

  - [Microsoft.VisualBasic.Compatibility.dll](#VBCompat)

  - [Microsoft.VisualBasic.Compatibility.Data.dll](#VBCompatData)

  - [Microsoft.VisualC.dll](#visualc)

<a name="obsolete_types_in_system_assemblies"></a>

## <a name="obsolete-types-in-system-assemblies"></a>Veraltete Typen in Systemassemblys

In den folgenden Tabellen sind die Typen aufgeführt, die in Systemassemblys als veraltet eingestuft wurden. Diese Assemblys werden zur allgemeinen Anwendungsentwicklung für .NET Framework verwendet.

<a name="mscorlib"></a>

### <a name="assembly-mscorlibdll"></a>Assembly: mscorlib.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.ExecutionEngineException?displayProperty=nameWithType>|Dieser Typ hat bisher einen nicht näher beschriebenen schwerwiegenden Fehler angegeben. Die Laufzeit löst diese Ausnahme nicht mehr aus, sodass dieser Typ veraltet ist.|
|<xref:System.Collections.CaseInsensitiveHashCodeProvider?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.StringComparer?displayProperty=nameWithType>.|
|<xref:System.Collections.IHashCodeProvider?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Collections.IEqualityComparer?displayProperty=nameWithType>.|
|<xref:System.Configuration.Assemblies.AssemblyHash?displayProperty=nameWithType>|Die <xref:System.Configuration.Assemblies.AssemblyHash>-Klasse ist veraltet.|
|<xref:System.Diagnostics.Contracts.Internal.ContractHelper?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5. Verwenden Sie stattdessen die <xref:System.Runtime.CompilerServices.ContractHelper?displayProperty=nameWithType>-Klasse im System.Runtime.CompilerServices-Namespace.|
|<xref:System.Reflection.Emit.UnmanagedMarshal?displayProperty=nameWithType>|Eine alternative API ist verfügbar: Geben Sie stattdessen das benutzerdefinierte Attribut <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> aus.|
|<xref:System.Runtime.InteropServices.BIND_OPTS?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.BIND_OPTS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.BINDPTR?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.BINDPTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.CALLCONV?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.CALLCONV?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.CONNECTDATA?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.CONNECTDATA?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.DESCKIND?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.DESCKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.DISPPARAMS?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.DISPPARAMS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.ELEMDESC?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.ELEMDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.EXCEPINFO?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.EXCEPINFO?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FILETIME?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.FILETIME?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCDESC?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.FUNCDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCFLAGS?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.FUNCFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.FUNCKIND?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.FUNCKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=nameWithType>|Dieses Attribut ist veraltet und wird in einer der nächsten Versionen entfernt.|
|<xref:System.Runtime.InteropServices.IDispatchImplType?displayProperty=nameWithType>|Das <xref:System.Runtime.InteropServices.IDispatchImplAttribute?displayProperty=nameWithType>-Objekt ist veraltet.|
|<xref:System.Runtime.InteropServices.IDLDESC?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IDLDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IDLFLAG?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IDLFLAG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.IMPLTYPEFLAGS?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IMPLTYPEFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.INVOKEKIND?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.INVOKEKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.LIBFLAGS?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.LIBFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.PARAMDESC?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.PARAMDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.PARAMFLAG?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.PARAMFLAG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.SetWin32ContextInIDispatchAttribute?displayProperty=nameWithType>|Dieses Attribut ist veraltet. Anwendungsdomänen beachten Aktivierungskontextgrenzen in IDispatch-Aufrufen nicht mehr.|
|<xref:System.Runtime.InteropServices.STATSTG?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.STATSTG?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.SYSKIND?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.SYSKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEATTR?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPEATTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEDESC?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPEDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEFLAGS?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPEFLAGS?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPEKIND?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPEKIND?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.TYPELIBATTR?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.TYPELIBATTR?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIBindCtx?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IBindCtx?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIConnectionPoint?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIConnectionPointContainer?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumConnectionPoints?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumConnectionPoints?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumConnections?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumConnections?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumMoniker?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumMoniker?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumString?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumString?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIEnumVARIANT?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IEnumVARIANT?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIMoniker?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IMoniker?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIPersistFile?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IPersistFile?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIRunningObjectTable?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IRunningObjectTable?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMIStream?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.IStream?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeComp?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.ITypeComp?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeInfo?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.UCOMITypeLib?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.ITypeLib?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.VARDESC?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.VARDESC?displayProperty=nameWithType>.|
|<xref:System.Runtime.InteropServices.VARFLAGS?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.Runtime.InteropServices.ComTypes.VARFLAGS?displayProperty=nameWithType> .|
|<xref:System.Security.SecurityCriticalScope?displayProperty=nameWithType>|<xref:System.Security.SecurityCriticalScope> wird nur für .NET 2.0-Transparenzkompatibilität verwendet.|
|<xref:System.Security.SecurityTreatAsSafeAttribute?displayProperty=nameWithType>|<xref:System.Security.SecurityTreatAsSafeAttribute> wird nur für .NET 2.0-Transparenzkompatibilität verwendet. Verwenden Sie stattdessen <xref:System.Security.SecuritySafeCriticalAttribute?displayProperty=nameWithType>.|
|<xref:System.Security.Policy.FirstMatchCodeGroup?displayProperty=nameWithType>|Dieser Typ ist veraltet und wird in einem der nächsten Releases von .NET Framework entfernt.|
|<xref:System.Security.Policy.PermissionRequestEvidence?displayProperty=nameWithType>|Die Deklarationssicherheit auf Assemblyebene wurde als veraltet eingestuft und wird von der CLR nicht mehr als Standardeinstellung erzwungen.|
|<xref:System.Security.Policy.UnionCodeGroup?displayProperty=nameWithType>|Dieser Typ ist veraltet und wird in einem der nächsten Releases von .NET Framework entfernt.|

[Zurück nach oben](#introduction)

<a name="Core"></a>

### <a name="assembly-systemcoredll"></a>Assembly: System.Core.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Runtime.CompilerServices.ExecutionScope?displayProperty=nameWithType>|Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Verwenden Sie diesen Typ nicht.|

[Zurück nach oben](#introduction)

<a name="data"></a>

### <a name="assembly-systemdatadll"></a>Assembly: System.Data.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Data.DataSysDescriptionAttribute?displayProperty=nameWithType>|<xref:System.Data.DataSysDescriptionAttribute> ist veraltet.|
|<xref:System.Data.PropertyAttributes?displayProperty=nameWithType>|<xref:System.Data.PropertyAttributes> ist veraltet.|
|<xref:System.Data.TypedDataSetGenerator?displayProperty=nameWithType>|Die <xref:System.Data.TypedDataSetGenerator>-Klasse wird in einer der nächsten Versionen entfernt. Verwenden Sie <xref:System.Data.Design.TypedDataSetGenerator?displayProperty=nameWithType> in "System.Design.dll".|
|<xref:System.Xml.XmlDataDocument?displayProperty=nameWithType>|Die <xref:System.Xml.XmlDataDocument>-Klasse wird in einer der nächsten Versionen entfernt.|

[Zurück nach oben](#introduction)

<a name="oracleclient"></a>

### <a name="assembly-systemdataoracleclientdll"></a>Assembly: System.Data.OracleClient.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Data.OracleClient.OracleClientFactory?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleClientFactory> ist veraltet.|
|<xref:System.Data.OracleClient.OracleCommand?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleCommand> ist veraltet.|
|<xref:System.Data.OracleClient.OracleCommandBuilder?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleCommandBuilder> ist veraltet.|
|<xref:System.Data.OracleClient.OracleConnection?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleConnection> ist veraltet.|
|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder> ist veraltet.|
|<xref:System.Data.OracleClient.OracleDataAdapter?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OracleDataAdapter> ist veraltet.|
|<xref:System.Data.OracleClient.OraclePermission?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OraclePermission> ist veraltet.|
|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=nameWithType>|<xref:System.Data.OracleClient.OraclePermissionAttribute?displayProperty=nameWithType> ist veraltet.|

[Zurück nach oben](#introduction)

<a name="design"></a>

### <a name="assembly-systemdesigndll"></a>Assembly: System.Design.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.ComponentModel.Design.LocalizationExtenderProvider?displayProperty=nameWithType>|Diese Klasse ist veraltet. Verwenden Sie stattdessen <xref:System.ComponentModel.Design.Serialization.CodeDomLocalizationProvider?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.DataBindingCollectionConverter?displayProperty=nameWithType>|Die Verwendung dieses Typs wird nicht empfohlen, da die Bearbeitung von Datenbindungen über <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=nameWithType> gestartet wird, anstatt über das Eigenschaftenraster.|
|<xref:System.Web.UI.Design.DataBindingCollectionEditor?displayProperty=nameWithType>|Die Verwendung dieses Typs wird nicht empfohlen, da die Bearbeitung von Datenbindungen über <xref:System.ComponentModel.Design.DesignerActionList?displayProperty=nameWithType> gestartet wird, anstatt über das Eigenschaftenraster.|
|<xref:System.Web.UI.Design.IControlDesignerBehavior?displayProperty=nameWithType>|Die empfohlenen Alternativen sind <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=nameWithType> und <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.IHtmlControlDesignerBehavior?displayProperty=nameWithType>|Die empfohlenen Alternativen sind <xref:System.Web.UI.Design.IControlDesignerTag?displayProperty=nameWithType> und <xref:System.Web.UI.Design.IControlDesignerView?displayProperty=nameWithType>.|
|<xref:System.Web.UI.Design.ITemplateEditingFrame?displayProperty=nameWithType>|Die Verwendung dieses Typs wird nicht empfohlen, da die Vorlagenbearbeitung in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> behandelt wird. Machen Sie zum Unterstützen der Vorlagenbearbeitung die Vorlagendaten in der <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType>-Eigenschaft verfügbar, und rufen Sie <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType> auf.|
|<xref:System.Web.UI.Design.IWebFormReferenceManager?displayProperty=nameWithType>|Die empfohlene Alternative ist <xref:System.Web.UI.Design.WebFormsReferenceManager?displayProperty=nameWithType>. Das <xref:System.Web.UI.Design.WebFormsReferenceManager>-Objekt enthält zusätzliche Funktionalität und ermöglicht eine stärkere Erweiterbarkeit. Verwenden Sie die <xref:System.Web.UI.Design.WebFormsReferenceManager>-Eigenschaft des `RootDesigner.ReferenceManager`-Objekts, um das <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>-Objekt abzurufen.|
|<xref:System.Web.UI.Design.IWebFormsDocumentService?displayProperty=nameWithType>|Die empfohlene Alternative ist <xref:System.Web.UI.Design.WebFormsRootDesigner?displayProperty=nameWithType>. Das <xref:System.Web.UI.Design.WebFormsRootDesigner>-Objekt enthält zusätzliche Funktionalität und ermöglicht eine stärkere Erweiterbarkeit. Verwenden Sie die <xref:System.Web.UI.Design.WebFormsRootDesigner>-Eigenschaft des <xref:System.Web.UI.Design.ControlDesigner.RootDesigner%2A>-Objekts, um das <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType>-Objekt abzurufen.|
|<xref:System.Web.UI.Design.ITemplateEditingService?displayProperty=nameWithType>|Die Verwendung dieses Typs wird nicht empfohlen, da die Vorlagenbearbeitung in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> behandelt wird. Machen Sie zum Unterstützen der Vorlagenbearbeitung die Vorlagendaten in der <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType>-Eigenschaft verfügbar, und rufen Sie <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType> auf.|
|<xref:System.Web.UI.Design.ReadWriteControlDesigner?displayProperty=nameWithType>|Die empfohlene Alternative ist das <xref:System.Web.UI.Design.ContainerControlDesigner?displayProperty=nameWithType>-Objekt, da es ein <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType>-Objekt zum Bearbeiten des Inhalts verwendet. Designerbereiche ermöglichen eine bessere Steuerung des zu bearbeitenden Inhalts.|
|<xref:System.Web.UI.Design.TemplateEditingService?displayProperty=nameWithType>|Die Verwendung dieses Typs wird nicht empfohlen, da die Vorlagenbearbeitung in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> behandelt wird. Machen Sie zum Unterstützen der Vorlagenbearbeitung die Vorlagendaten in der <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType>-Eigenschaft verfügbar, und rufen Sie <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType> auf.|
|<xref:System.Web.UI.Design.TemplateEditingVerb?displayProperty=nameWithType>|Die Verwendung dieses Typs wird nicht empfohlen, da die Vorlagenbearbeitung in <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> behandelt wird. Machen Sie zum Unterstützen der Vorlagenbearbeitung die Vorlagendaten in der <xref:System.Web.UI.Design.ControlDesigner.TemplateGroups%2A?displayProperty=nameWithType>-Eigenschaft verfügbar, und rufen Sie <xref:System.Web.UI.Design.ControlDesigner.SetViewFlags%2A?displayProperty=nameWithType> auf.|
|<xref:System.Web.UI.Design.WebControls.CalendarAutoFormatDialog?displayProperty=nameWithType>|Die Verwendung dieses Typs wird nicht empfohlen, da das Dialogfeld "AutoFormat" vom Designerhost gestartet wird. Die Liste der verfügbaren automatischen Formatierungen wird für <xref:System.Web.UI.Design.ControlDesigner?displayProperty=nameWithType> in der <xref:System.Web.UI.Design.ControlDesigner.AutoFormats%2A?displayProperty=nameWithType>-Eigenschaft verfügbar gemacht.|
|<xref:System.Web.UI.Design.WebControls.PanelDesigner?displayProperty=nameWithType>|Die empfohlene Alternative ist das <xref:System.Web.UI.Design.WebControls.PanelContainerDesigner?displayProperty=nameWithType>-Objekt, da es ein <xref:System.Web.UI.Design.EditableDesignerRegion?displayProperty=nameWithType>-Objekt zum Bearbeiten des Inhalts verwendet. Designerbereiche ermöglichen eine bessere Steuerung des zu bearbeitenden Inhalts.|

[Zurück nach oben](#introduction)

<a name="system"></a>

### <a name="assembly-systemdll"></a>Assembly: System.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.ComponentModel.IComNativeDescriptorHandler?displayProperty=nameWithType>|Diese Schnittstelle ist veraltet. Fügen Sie stattdessen einen <xref:System.ComponentModel.TypeDescriptionProvider?displayProperty=nameWithType> hinzu, um den Typ <xref:System.ComponentModel.TypeDescriptor.ComObjectType%2A?displayProperty=nameWithType> zu behandeln.|
|<xref:System.ComponentModel.RecommendedAsConfigurableAttribute?displayProperty=nameWithType>|Verwenden Sie stattdessen <xref:System.ComponentModel.SettingsBindableAttribute?displayProperty=nameWithType>, um mit dem neuen Einstellungsmodell zu arbeiten.|
|<xref:System.ComponentModel.Design.Serialization.RootDesignerSerializerAttribute?displayProperty=nameWithType>|Dieses Attribut ist veraltet. Verwenden Sie stattdessen <xref:System.ComponentModel.Design.Serialization.DesignerSerializerAttribute?displayProperty=nameWithType>.|
|<xref:System.Diagnostics.DiagnosticsConfigurationHandler?displayProperty=nameWithType>|Diese Klasse ist veraltet.|
|<xref:System.Diagnostics.PerformanceCounterManager?displayProperty=nameWithType>|Diese Klasse ist veraltet. Verwenden Sie stattdessen die Leistungsindikatoren über die <xref:System.Diagnostics.PerformanceCounter?displayProperty=nameWithType>-Klasse.|
|<xref:System.Net.GlobalProxySelection?displayProperty=nameWithType>|Diese Klasse ist veraltet. Verwenden Sie stattdessen <xref:System.Net.WebRequest.DefaultWebProxy%2A?displayProperty=nameWithType>, um auf den globalen Standardproxy zuzugreifen und diesen festzulegen. Verwenden Sie "null" anstelle von <xref:System.Net.GlobalProxySelection.GetEmptyWebProxy%2A?displayProperty=nameWithType>.|
|<xref:System.Net.Sockets.SocketClientAccessPolicyProtocol?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|

[Zurück nach oben](#introduction)

<a name="enterpriseservices"></a>

### <a name="assembly-systementerpriseservicesdll"></a>Assembly: System.EnterpriseServices.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.EnterpriseServices.RegistrationHelperTx?displayProperty=nameWithType>|Die <xref:System.EnterpriseServices.RegistrationHelperTx>-Klasse ist veraltet.|

[Zurück nach oben](#introduction)

<a name="net"></a>

### <a name="assembly-systemnetdll"></a>Assembly: System.Net.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Net.INetworkProgress?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Net.IUnsafeWebRequestCreate?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Net.NetworkProgressChangedEventArgs?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Net.UiSynchronizationContext?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Net.Sockets.HttpPolicyDownloaderProtocol?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Net.Sockets.SecurityCriticalAction?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Net.Sockets.SocketPolicy?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Net.Sockets.UdpAnySourceMulticastClient?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Net.Sockets.UdpSingleSourceMulticastClient?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|

[Zurück nach oben](#introduction)

<a name="servicemodel"></a>

### <a name="assembly-systemservicemodeldll"></a>Assembly: System.ServiceModel.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.ServiceModel.NetPeerTcpBinding?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|
|<xref:System.ServiceModel.Channels.HttpCookieContainerBindingElement?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Dieser Typ ist veraltet. Um HTTP <xref:System.Net.CookieContainer> zu aktivieren, verwenden Sie die `AllowCookies`-Eigenschaft auf der HTTP-Bindung oder auf <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.|
|<xref:System.ServiceModel.Channels.PeerCustomResolverBindingElement?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|
|<xref:System.ServiceModel.Channels.PeerTransportBindingElement?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingCollectionElement?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|
|<xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|
|<xref:System.ServiceModel.Configuration.PeerTransportElement?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|
|<xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Peerchannelfunktion ist veraltet und wird demnächst entfernt.|

[Zurück nach oben](#introduction)

<a name="web"></a>

### <a name="assembly-systemwebdll"></a>Assembly: System.Web.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Web.Configuration.PassportAuthentication?displayProperty=nameWithType>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](https://account.microsoft.com/account/Account?destrt=home-index) abgelöst.|
|<xref:System.Web.Mail.MailAttachment?displayProperty=nameWithType>|Die empfohlene Alternative ist <xref:System.Net.Mail.Attachment?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailEncoding?displayProperty=nameWithType>|Die empfohlene Alternative ist <xref:System.Net.Mime.TransferEncoding?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailFormat?displayProperty=nameWithType>|Die empfohlene Alternative ist <xref:System.Net.Mail.MailMessage.IsBodyHtml%2A?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType>|Die empfohlene Alternative ist <xref:System.Net.Mail.MailMessage?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.MailPriority?displayProperty=nameWithType>|Die empfohlene Alternative ist <xref:System.Net.Mail.MailPriority?displayProperty=nameWithType>.|
|<xref:System.Web.Mail.SmtpMail?displayProperty=nameWithType>|Die empfohlene Alternative ist <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>.|
|<xref:System.Web.Security.PassportAuthenticationEventArgs?displayProperty=nameWithType>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](https://account.microsoft.com/account/Account?destrt=home-index) abgelöst.|
|<xref:System.Web.Security.PassportAuthenticationEventHandler?displayProperty=nameWithType>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](https://account.microsoft.com/account/Account?destrt=home-index) abgelöst.|
|<xref:System.Web.Security.PassportAuthenticationModule?displayProperty=nameWithType>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](https://account.microsoft.com/account/Account?destrt=home-index) abgelöst.|
|<xref:System.Web.Security.PassportIdentity?displayProperty=nameWithType>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](https://account.microsoft.com/account/Account?destrt=home-index) abgelöst.|
|<xref:System.Web.Security.PassportPrincipal?displayProperty=nameWithType>|Dieser Typ ist veraltet. Das Passport-Authentifizierungsprodukt wird nicht mehr unterstützt und wurde durch ein [Microsoft-Konto](https://account.microsoft.com/account/Account?destrt=home-index) abgelöst.|
|<xref:System.Web.UI.ObjectConverter?displayProperty=nameWithType>|Die empfohlenen Alternativen sind <xref:System.Convert?displayProperty=nameWithType> und <xref:System.String.Format%2A?displayProperty=nameWithType>.|

[Zurück nach oben](#introduction)

<a name="mobile"></a>

### <a name="assembly-systemwebmobiledll"></a>Assembly: System.Web.Mobile.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Web.Mobile.CookielessData?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFilterElement?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFilterElementCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.DeviceFiltersSection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.ErrorHandlerModule?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileCapabilities?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileDeviceCapabilitiesSectionHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileErrorInfo?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.Mobile.MobileFormsAuthentication?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.IMobileDesigner?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.IMobileWebFormServices?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.MobileResource?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.Converters.DataFieldConverter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.Design.MobileControls.Converters.DataMemberConverter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.AdRotator?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Alignment?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ArrayListCollectionBase?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.BaseValidator?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.BooleanOption?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Calendar?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Command?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CommandFormat?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CompareValidator?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Constants?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlElement?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlElementCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ControlPager?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.CustomValidator?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DesignerAdapterAttribute?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceElement?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceElementCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceOverridableAttribute?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecific?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoice?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificChoiceTemplateContainer?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.DeviceSpecificControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ErrorFormatterPage?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FontInfo?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FontSize?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Form?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FormControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.FormMethod?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IControlAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Image?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IObjectListFieldCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.IPageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ItemPager?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ITemplateable?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Label?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Link?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.List?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListCommandEventArgs?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListCommandEventHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDataBindEventArgs?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDataBindEventHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListDecoration?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ListSelectType?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralLink?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralText?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralTextContainerControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LiteralTextControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LoadItemsEventArgs?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.LoadItemsEventHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControl?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlsSection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileControlsSectionHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItem?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItemCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileListItemType?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobilePage?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileTypeNameConverter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.MobileUserControl?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectList?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommand?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventArgs?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListCommandEventHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventArgs?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListDataBindEventHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListField?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListFieldCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListItem?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListItemCollection?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventArgs?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListSelectEventHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventArgs?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListShowCommandsEventHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListTitleAttribute?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ObjectListViewMode?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PagedControl?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PagerStyle?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Panel?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PanelControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PersistNameAttribute?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.PhoneCall?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RangeValidator?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RegularExpressionValidator?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.RequiredFieldValidator?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.SelectionList?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Style?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.StyleSheet?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.StyleSheetControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TemplateContainer?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextBox?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextBoxControlBuilder?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextControl?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextView?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.TextViewElement?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.ValidationSummary?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Wrapping?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCalendarAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlCommandAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlFormAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlImageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlLinkAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlMobileTextWriter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlPhoneCallAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlSelectionListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ChtmlTextBoxAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.ControlAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCalendarAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlCommandAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlControlAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlFormAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlImageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLabelAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLinkAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlLiteralTextAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlMobileTextWriter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlObjectListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPanelAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlPhoneCallAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlSelectionListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextBoxAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlTextViewAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidationSummaryAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.HtmlValidatorAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.MobileTextWriter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.MultiPartWriter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlMobileTextWriter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.UpWmlPageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlCalendarAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlCommandAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlControlAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlFormAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlImageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLabelAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLinkAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlLiteralTextAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlMobileTextWriter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlObjectListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPanelAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPhoneCallAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlPostFieldType?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlSelectionListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextBoxAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlTextViewAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidationSummaryAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.WmlValidatorAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.Doctype?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.StyleSheetLocation?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCalendarAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCommandAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlControlAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlCssHandler?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlFormAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlImageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLabelAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLinkAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlLiteralTextAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlMobileTextWriter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlObjectListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPageAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPanelAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlPhoneCallAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlSelectionListAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextBoxAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlTextViewAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidationSummaryAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|
|<xref:System.Web.UI.MobileControls.Adapters.XhtmlAdapters.XhtmlValidatorAdapter?displayProperty=nameWithType>|Die Assembly "System.Web.Mobile.dll" ist veraltet und sollte nicht mehr verwendet werden. Informationen zum Entwickeln mobiler ASP.NET-Anwendungen finden Sie auf den Webseiten über [mobile Apps und Websites mit ASP.NET](/aspnet/mobile/overview).|

[Zurück nach oben](#introduction)

<a name="workflow_activities"></a>

### <a name="assembly-systemworkflowactivitiesdll"></a>Assembly: System.Workflow.Activities.dll

|Typ|Meldung|
|----------|-------------|
|Alle Typen im <xref:System.Workflow.Activities?displayProperty=nameWithType>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Configuration.ActiveDirectoryRoleFactoryConfiguration?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleActionTrackingEvent?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleConditionReference?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.Activities.Rules.RuleSetReference?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|

[Zurück nach oben](#introduction)

<a name="workflow_componentmodel"></a>

### <a name="assembly-systemworkflowcomponentmodeldll"></a>Assembly: System.Workflow.ComponentModel.dll

|Typ|Meldung|
|----------|-------------|
|Alle Typen im <xref:System.Workflow.ComponentModel>-Namespace außer <xref:System.Workflow.ComponentModel.GetValueOverride?displayProperty=nameWithType> und <xref:System.Workflow.ComponentModel.SetValueOverride?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|Alle Typen im <xref:System.Workflow.ComponentModel.Compiler>-Namespace außer <xref:System.Workflow.ComponentModel.Compiler.ValidationError?displayProperty=nameWithType> und <xref:System.Workflow.ComponentModel.Compiler.ValidationErrorCollection?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|Alle Typen im <xref:System.Workflow.ComponentModel.Design>-Namespace außer <xref:System.Workflow.ComponentModel.Design.ConnectorEventHandler>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializationManager?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityCodeDomSerializer?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityMarkupSerializer?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivitySurrogateSelector?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.ActivityTypeCodeDomSerializer?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.CompositeActivityMarkupSerializer?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.ComponentModel.Serialization.DependencyObjectCodeDomSerializer?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|

[Zurück nach oben](#introduction)

<a name="workflow_runtime"></a>

### <a name="assembly-systemworkflowruntimedll"></a>Assembly: System.Workflow.Runtime.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Activities.Statements.Interop?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br />Die Workflow Foundation 3.0-Typen sind veraltet. Verwenden Sie stattdessen die Workflow 4.0-Typen von <xref:System.Activities>\*.|
|<xref:System.Activities.Tracking.InteropTrackingRecord?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br />Die Workflow Foundation 3.0-Typen sind veraltet. Verwenden Sie stattdessen die Workflow 4.0-Typen von <xref:System.Activities>\*.|
|Alle Typen im <xref:System.Workflow.Runtime>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|Alle Typen im <xref:System.Workflow.Runtime.Configuration>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|Alle Typen im <xref:System.Workflow.Runtime.DebugEngine>-Namespace außer <xref:System.Workflow.Runtime.DebugEngine.DebugEngineCallback>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|Alle Typen im <xref:System.Workflow.Runtime.Hosting>-Namespace außer <xref:System.Workflow.Runtime.Hosting.WorkflowCommitWorkBatchService.CommitWorkBatchCallback>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|
|Alle Typen im <xref:System.Workflow.Runtime.Tracking>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die System.Workflow.\*-Typen sind veraltet. Verwenden Sie stattdessen die neuen Typen von <xref:System.Activities>\*.|

[Zurück nach oben](#introduction)

<a name="workflowservices"></a>

### <a name="assembly-systemworkflowservicesdll"></a>Assembly: System.WorkflowServices.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.ServiceModel.WorkflowServiceHost?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Activation.WorkflowServiceHostFactory?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Activities.Description.WorkflowRuntimeEndpoint?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.ExtendedWorkflowRuntimeServiceElementCollection?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.PersistenceProviderElement?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Configuration.WorkflowRuntimeElement?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.DurableOperationAttribute?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.DurableServiceAttribute?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.PersistenceProviderBehavior?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.UnknownExceptionAction?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Description.WorkflowRuntimeBehavior?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Dispatcher.DurableOperationContext?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.InstanceLockException?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.InstanceNotFoundException?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.LockingPersistenceProvider?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceException?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceProvider?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.PersistenceProviderFactory?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.ServiceModel.Persistence.SqlPersistenceProviderFactory?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|Alle Typen im <xref:System.Workflow.Activities?displayProperty=nameWithType>-Namespace|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|
|<xref:System.Workflow.Runtime.Hosting.ChannelManagerService?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die WF 3-Typen sind veraltet. Verwenden Sie stattdessen die neuen WF 4-Typen von <xref:System.Activities>\*.|

[Zurück nach oben](#introduction)

<a name="xaml"></a>

### <a name="assembly-systemxamldll"></a>Assembly: System.Xaml.dll

|Typ|Nachricht|
|----------|-------------|
|<xref:System.Windows.Markup.AcceptedMarkupExtensionExpressionTypeAttribute?displayProperty=nameWithType>|Wird vom XAML-Parser nicht verwendet. Sehen Sie unter <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute?displayProperty=nameWithType> nach.|

[Zurück nach oben](#introduction)

<a name="xml"></a>

### <a name="assembly-systemxmldll"></a>Assembly: System.Xml.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Xml.IApplicationResourceStreamResolver?displayProperty=nameWithType>|Zuerst veraltet in .NET Framework 4.5.<br /><br /> Die Verwendung dieses Typs generiert einen Compilerfehler.<br /><br /> Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Xml.Schema.XmlSchemaCollection?displayProperty=nameWithType>|Verwenden Sie <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> für die Schemakompilierung und -validierung.|
|<xref:System.Xml.XmlValidatingReader?displayProperty=nameWithType>|Verwenden Sie stattdessen ein <xref:System.Xml.XmlReader?displayProperty=nameWithType>-Objekt, das von der <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType>-Methode erstellt wird, mit dem entsprechenden <xref:System.Xml.XmlReaderSettings?displayProperty=nameWithType>-Objekt.|
|<xref:System.Xml.XmlXapResolver?displayProperty=nameWithType>|Die Verwendung dieses Typs generiert einen Compilerfehler. Diese API unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung vom Code aus vorgesehen.|
|<xref:System.Xml.Xsl.XslTransform?displayProperty=nameWithType>|Diese Klasse ist veraltet. Verwenden Sie stattdessen <xref:System.Xml.Xsl.XslCompiledTransform?displayProperty=nameWithType>.|

[Zurück nach oben](#introduction)

<a name="WindowsBase"></a>

### <a name="assembly-windowsbasedll"></a>Assembly: WindowsBase.dll

|Typ|Meldung|
|----------|-------------|
|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=nameWithType>|<xref:System.Windows.Markup.IReceiveMarkupExtension?displayProperty=nameWithType> ist veraltet. Diese Schnittstelle wird nicht mehr verwendet.|

[Zurück nach oben](#introduction)

<a name="obsolete_types_in_microsoft_assemblies"></a>

## <a name="obsolete-types-in-microsoft-assemblies"></a>Veraltete Typen in Microsoft-Assemblys

In den folgenden Abschnitten sind die veralteten Typen in Microsoft-Assemblys aufgeführt. Bei diesen Assemblys handelt es sich um zweckgebundene Assemblys, beispielsweise Assemblys, die auf eine einzelne Sprache abzielen (z. B. Microsoft.JScript.dll oder Microsoft.VisualC.dll).

<a name="IEHost"></a>

### <a name="assembly-iehostdll-and-ieexecexe"></a>Assembly: IEHost.dll und IEExec.exe

Die IEHost.dll-Assembly und die IEExec.exe-Assembly wurden aus .NET Framework entfernt. Alle zugehörigen Typen und Member sind veraltet und werden ab .NET Framework 4 nicht mehr unterstützt. Diese Assemblys wurden verwendet, um Windows Forms-Steuerelemente zu hosten und ausführbare Dateien in Internet Explorer auszuführen. Empfohlene Alternativen schließen ClickOnce, XAML-Browseranwendungen (XBAP) und Microsoft Silverlight ein.

[Zurück nach oben](#introduction)

<a name="Engine"></a>

### <a name="assembly-microsoftbuildenginedll"></a>Assembly: Microsoft.Build.Engine.dll

|Typ|Meldung|
|----------|-------------|
|<xref:Microsoft.Build.BuildEngine.Engine?displayProperty=nameWithType>|Diese Klasse ist veraltet. Verwenden Sie stattdessen bitte <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=nameWithType> aus der *Microsoft.Build*-Assembly.|
|<xref:Microsoft.Build.BuildEngine.Project?displayProperty=nameWithType>|Diese Klasse ist veraltet. Verwenden Sie stattdessen bitte <xref:Microsoft.Build.Evaluation.ProjectCollection?displayProperty=nameWithType> aus der *Microsoft.Build*-Assembly.|

[Zurück nach oben](#introduction)

<a name="jscript"></a>

### <a name="assembly-microsoftjscriptdll"></a>Assembly: Microsoft.JScript.dll

|Typ|Meldung|
|----------|-------------|
|<xref:Microsoft.JScript.Vsa.BaseVsaEngine?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.BaseVsaSite?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.BaseVsaStartup?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaCodeItem?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaEngine?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaError?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaGlobalItem?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaItem?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaItems?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaPersistSite?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaReferenceItem?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.IJSVsaSite?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaError?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaException?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaItemFlag?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.JSVsaItemType?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.ResInfo?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|
|<xref:Microsoft.JScript.Vsa.VsaEngine?displayProperty=nameWithType>|Dieser Typ ist seit Visual Studio 2005 veraltet. Für dieses Feature gibt es keinen Ersatz. Weitere Informationen finden Sie in der Dokumentation zu <xref:System.CodeDom.Compiler.ICodeCompiler?displayProperty=nameWithType>.|

[Zurück nach oben](#introduction)

<a name="VBCompat"></a>

### <a name="assembly-microsoftvisualbasiccompatibilitydll"></a>Assembly: Microsoft.VisualBasic.Compatibility.dll

Weitere Informationen zum Migrieren von Visual Basic 6 finden Sie unter [Visual Basic 6.0 Resource Center (Ressourcencenter für Visual Basic 6.0)](https://docs.microsoft.com/previous-versions/visualstudio/visual-basic-6/visual-basic-6.0-documentation).

|Typ|Meldung|
|----------|-------------|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseControlArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseOcxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ButtonArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CheckedListBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ColorDialogArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ComboBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBox?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DirListBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBox?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DriveListBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBox?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FileListBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FixedLengthString?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FontDialogArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.FormShowConstants?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.GroupBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.HScrollBarArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ImageListArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LabelArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListBoxItem?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ListViewArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.LoadResConstants?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MaskedTextBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MenuItemArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MouseButtonConstants?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.OpenFileDialogArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PanelArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PictureBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.PrintDialogArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ProgressBarArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RadioButtonArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.RichTextBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SaveFileDialogArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ScaleMode?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ShiftConstants?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusBarArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.StatusStripArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.Support?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TabControlArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TextBoxArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TimerArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolBarArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ToolStripMenuItemArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.TreeViewArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.VScrollBarArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebBrowserArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClass?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassContainingClassNotOptional?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassCouldNotFindEvent?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemCannotBeCurrentWebItem?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassNextItemRespondNotFound?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassUserWebClassNameNotOptional?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebClassFileNameNotOptional?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebClassWebItemNotValid?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItem?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemAssociatedWebClassNotOptional?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemClosingTagNotFound?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadEmbeddedResource?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemCouldNotLoadTemplateFile?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNameNotOptional?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemNoTemplateSpecified?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemTooManyNestedTags?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.WebItemUnexpectedErrorReadingTemplateFile?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ZOrderConstants?displayProperty=nameWithType>|Dieser Member ist veraltet.|

[Zurück nach oben](#introduction)

<a name="VBCompatData"></a>

### <a name="assembly-microsoftvisualbasiccompatibilitydatadll"></a>Assembly: Microsoft.VisualBasic.Compatibility.Data.dll

|Typ|Meldung|
|----------|-------------|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.BOFActionEnum?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EndOfRecordsetDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.EOFActionEnum?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.ErrorDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchCompleteDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FetchProgressDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.FieldChangeCompleteDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.MoveCompleteDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.OrientationEnum?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordChangeCompleteDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.RecordsetChangeCompleteDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeFieldDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillChangeRecordsetDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODC.WillMoveDelegate?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.ADODCArray?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BaseDataEnvironment?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.BindingCollectionEnumerator?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.CONNECTDATA?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBBINDING?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBCOLUMNINFO?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBID?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBinding?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBindingCollection?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBKINDENUM?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.DBPROPIDSET?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IAccessor?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IChapteredRowset?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IColumnsInfo?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPoint?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IConnectionPointContainer?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormat?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IDataFormatDisp?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnectionPoints?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IEnumConnections?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPosition?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowPositionChange?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowset?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetChange?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetIdentity?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetInfo?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.IRowsetNotify?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBinding?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.MBindingCollection?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.SRDescriptionAttribute?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UGUID?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UNAME?displayProperty=nameWithType>|Dieser Member ist veraltet.|
|<xref:Microsoft.VisualBasic.Compatibility.VB6.UpdateMode?displayProperty=nameWithType>|Dieser Member ist veraltet.|

[Zurück nach oben](#introduction)

<a name="visualc"></a>

### <a name="assembly-microsoftvisualcdll"></a>Assembly: Microsoft.VisualC.dll

|Typ|Meldung|
|----------|-------------|
|<xref:Microsoft.VisualC.DebugInfoInPDBAttribute?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.DecoratedNameAttribute?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.IsConstModifier?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.IsCXXReferenceModifier?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.IsLongModifier?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.IsSignedModifier?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.IsVolatileModifier?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.MiscellaneousBitsAttribute?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.NeedsCopyConstructorModifier?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|
|<xref:Microsoft.VisualC.NoSignSpecifiedModifier?displayProperty=nameWithType>|"Microsoft.VisualC.dll" ist eine veraltete Assembly und ist nur aus Gründen der Abwärtskompatibilität vorhanden.|

## <a name="see-also"></a>Siehe auch

- [Veraltete Elemente in der Klassenbibliothek](whats-obsolete.md)
- [Veraltete Member](obsolete-members.md)
