---
title: <startup>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153729"
---
# <a name="startup-element"></a>\<Start>-Element

Gibt allgemeine Laufzeitstartinformationen an.

[**\<Konfiguration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<Startup->**  

## <a name="syntax"></a>Syntax

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attributes

|attribute|Beschreibung|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|Optionales Attribut.<br /><br /> Gibt an, ob die .NET Framework 2.0-Laufzeitaktivierungsrichtlinie aktiviert oder die .NET Framework 4-Aktivierungsrichtlinie verwendet werden soll.|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>useLegacyV2RuntimeActivationPolicy-Attribut

|value|Beschreibung|
|-----------|-----------------|
|`true`|Aktivieren Sie .NET Framework 2.0-Laufzeitaktivierungsrichtlinie für die gewählte Laufzeit, d. h. ältere Laufzeitaktivierungstechniken (z. B. [die CorBindToRuntimeEx-Funktion)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)an die laufzeitweise zu binden, die aus der Konfigurationsdatei ausgewählt wurde, anstatt sie mit CLR-Version 2.0 zu deckeln. Wenn also CLR-Version 4 oder höher aus der Konfigurationsdatei ausgewählt wird, werden Assemblys im gemischten Modus, die mit früheren Versionen von .NET Framework erstellt wurden, mit der ausgewählten CLR-Version geladen. Durch Festlegen dieses Werts wird verhindert, dass CLR-Version 1.1 oder CLR-Version 2.0 in denselben Prozess geladen wird, wodurch das Prozess-Side-by-Side-Feature effektiv deaktiviert wird.|
|`false`|Verwenden Sie die Standardaktivierungsrichtlinie für .NET Framework 4 und höher, d. h. die Verwendung von Legacy-Laufzeitaktivierungstechniken zum Laden von CLR-Version 1.1 oder 2.0 in den Prozess. Durch Festlegen dieses Werts wird verhindert, dass Assemblys mit gemischtem Modus in .NET Framework 4 oder höher geladen werden, es sei denn, sie wurden mit .NET Framework 4 oder höher erstellt. Dies ist der Standardwert.|

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[\<erforderlichDauer>](requiredruntime-element.md)|Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt. Anwendungen, die mit Derlaufzeitversion 1.1 oder höher erstellt wurden, sollten das ** \<unterstützteRuntime>-Element** verwenden.|
|[\<unterstützteRuntime->](supportedruntime-element.md)|Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|

## <a name="remarks"></a>Bemerkungen

 Das ** \<unterstützteRuntime->-Element** sollte von allen Anwendungen verwendet werden, die mit Version 1.1 oder höher der Laufzeit erstellt wurden. Anwendungen, die nur Version 1.0 der Laufzeit unterstützen, müssen das ** \<erforderlicheRuntime->-Element** verwenden.

 Der Startcode für eine in Microsoft Internet ** \<** Explorer gehostete Anwendung ignoriert den Start>-Elements und seine untergeordneten Elemente.

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>Das useLegacyV2RuntimeActivationPolicy-Attribut

 Dieses Attribut ist nützlich, wenn Ihre Anwendung ältere Aktivierungspfade verwendet, z. B. die [CorBindToRuntimeTimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten, dass diese Pfade Version 4 der CLR anstelle einer früheren Version aktivieren, oder wenn Ihre Anwendung mit .NET Framework 4 erstellt wird, aber von einer Assembly im gemischten Modus abhängig ist, die mit einer früheren Version von .NET Framework erstellt wurde. Legen Sie in diesen `true`Szenarien das Attribut auf .

> [!NOTE]
> Festlegen des `true` Attributs, um zu verhindern, dass CLR-Version 1.1 oder CLR-Version 2.0 in denselben Prozess geladen wird, wodurch das prozessübergreifende Side-by-Side-Feature effektiv deaktiviert wird (siehe [Side-by-Side-Ausführung für COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).

## <a name="example"></a>Beispiel

 Das folgende Beispiel zeigt, wie Sie die Laufzeitversion in einer Konfigurationsdatei angeben.

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Starteinstellungsschema](index.md)
- [Schema der Konfigurationsdatei](../index.md)
- [Gewusst wie: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder neueren Versionen](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [Parallele Ausführung für COM-Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [Prozessinterne parallele Ausführung](../../../deployment/in-process-side-by-side-execution.md)
