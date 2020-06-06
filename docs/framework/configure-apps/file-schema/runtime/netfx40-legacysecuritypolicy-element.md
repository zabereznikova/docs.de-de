---
title: <NetFx40_LegacySecurityPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
ms.openlocfilehash: d5192eb56bb8b640544bdc52a0bb9d8a5277efef
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116254"
---
# <a name="netfx40_legacysecuritypolicy-element"></a>\<NetFx40_LegacySecurityPolicy>-Element

Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_LegacySecurityPolicy>**  

## <a name="syntax"></a>Syntax

```xml
<NetFx40_LegacySecurityPolicy
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Runtime die Legacy-CAS-Richtlinie verwendet|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|BESCHREIBUNG|
|-----------|-----------------|
|`false`|Die Common-CAS-Richtlinie wird von der Laufzeit nicht verwendet. Dies ist die Standardeinstellung.|
|`true`|Die Laufzeit verwendet die Legacy-CAS-Richtlinie.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|

## <a name="remarks"></a>Bemerkungen

In den .NET Framework Version 3,5 und früheren Versionen ist die CAS-Richtlinie immer wirksam. In der .NET Framework 4 muss die CAS-Richtlinie aktiviert werden.

Die CAS-Richtlinie ist Versions spezifisch. Benutzerdefinierte CAS-Richtlinien, die in früheren Versionen der .NET Framework vorhanden sind, müssen in der .NET Framework 4 neu angegeben werden.

Das Anwenden des- `<NetFx40_LegacySecurityPolicy>` Elements auf eine .NET Framework 4-Assembly wirkt sich nicht auf [Sicherheits transparenten Code](../../../misc/security-transparent-code.md)aus; die Transparenzregeln gelten weiterhin.

> [!IMPORTANT]
> Das Anwenden des- `<NetFx40_LegacySecurityPolicy>` Elements kann zu erheblichen Leistungseinbußen für Native Image-Assemblys führen, die vom [Native Image Generator (Ngen. exe)](../../../tools/ngen-exe-native-image-generator.md) erstellt werden, die nicht im globalen Assemblycache installiert sind. [global assembly cache](../../../app-domains/gac.md) Die Leistungsminderung wird dadurch verursacht, dass die Common Language Runtime die Assemblys nicht als systemeigene Images lädt, wenn das Attribut angewendet wird, was dazu führt, dass Sie als Just-in-Time-Assemblys geladen werden.

> [!NOTE]
> Wenn Sie in den Projekteinstellungen für das Visual Studio-Projekt eine Ziel .NET Framework Version angeben, die älter als die .NET Framework 4 ist, wird die CAS-Richtlinie aktiviert, einschließlich aller benutzerdefinierten CAS-Richtlinien, die Sie für diese Version angegeben haben. Sie können jedoch keine neuen .NET Framework 4-Typen und-Member verwenden. Sie können auch eine frühere Version der .NET Framework angeben, indem Sie das- [ \<supportedRuntime> Element](../startup/supportedruntime-element.md) im Schema der Start Einstellungen in der [Anwendungs Konfigurationsdatei](../../index.md)verwenden.

> [!NOTE]
> Bei der Syntax der Konfigurationsdatei wird die groß-/klein Sie sollten die Syntax verwenden, wie in den Abschnitten Syntax und example bereitgestellt.

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie die Legacy-CAS-Richtlinie für eine Anwendung aktiviert wird.

```xml
<configuration>
   <runtime>
      <NetFx40_LegacySecurityPolicy enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
