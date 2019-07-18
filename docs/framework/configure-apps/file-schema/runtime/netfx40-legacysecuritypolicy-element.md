---
title: <NetFx40_LegacySecurityPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5bfa5449ece1b24d4f47fe3e77e36b26bbe430c
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2019
ms.locfileid: "66689842"
---
# <a name="netfx40legacysecuritypolicy-element"></a>\<NetFx40_LegacySecurityPolicy >-Element

Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.

\<configuration>\
\<runtime>\
\<NetFx40_LegacySecurityPolicy>

## <a name="syntax"></a>Syntax

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Runtime die CAS-legacyrichtlinie verwendet.|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`false`|Die Runtime verwendet nicht CAS-legacyrichtlinie. Dies ist die Standardeinstellung.|
|`true`|Die Runtime verwendet die legacy-CAS-Richtlinie.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|

## <a name="remarks"></a>Hinweise

CAS-Richtlinie ist in der .NET Framework, Version 3.5 und früheren Versionen immer wirksam. In .NET Framework 4 muss CAS-Richtlinie aktiviert sein.

CAS-Richtlinie ist versionsspezifisch. Benutzerdefinierte CAS-Richtlinien, die in früheren Versionen von .NET Framework vorhanden sind, müssen in .NET Framework 4 erneut angegeben werden.

Anwenden der `<NetFx40_LegacySecurityPolicy>` Element auf eine Assembly von .NET Framework 4 hat keinen Einfluss auf [Sicherheitstransparenter Code](../../../../../docs/framework/misc/security-transparent-code.md); die Transparenzregeln gelten weiterhin.

> [!IMPORTANT]
> Anwenden der `<NetFx40_LegacySecurityPolicy>` Elements kann dazu führen, Leistungseinbußen für Assemblys systemeigener Abbilder, die erstellt werden, indem der [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) nicht im installierten der [globalen Assemblycache ](../../../../../docs/framework/app-domains/gac.md). Die Leistungsminderung wird verursacht, wenn die Unmöglichkeit der Runtime, die die Assemblys als native Bilder geladen werden, wenn das Attribut angewendet wird, und ihre wird als just-in-Time-Assemblys geladen.

> [!NOTE]
> Wenn Sie eine .NET Framework-Zielversion, die älter als .NET Framework 4 in den projekteinstellungen für Visual Studio-Projekt ist angeben, wird die CAS-Richtlinie aktiviert werden, einschließlich benutzerdefinierten CAS-Richtlinien, die Sie für diese Version angegeben. Allerdings werden Sie nicht neue .NET Framework 4-Typen und Member verwenden können. Sie können auch eine frühere Version von .NET Framework angeben, indem die [ \<SupportedRuntime >-Element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in das Schema für starteinstellungen in Ihrer [Konfigurationsdatei der Anwendung](../../../../../docs/framework/configure-apps/index.md).

> [!NOTE]
> Syntax von Konfigurationsdateien wird Groß-/Kleinschreibung beachtet. Sie sollten die Syntax verwenden, wie in den Abschnitten zu Syntax und Beispiel bereitgestellt.

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie die legacy-CAS-Richtlinie für eine Anwendung zu aktivieren.

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
