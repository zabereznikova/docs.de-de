---
title: <bypassTrustedAppStrongNames>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
ms.openlocfilehash: 96361a6742d1d2f76cb237344189d3277d7c8069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73739087"
---
# <a name="bypasstrustedappstrongnames-element"></a>\<bypassTrustedAppStrongNames>-Element

Gibt an, ob die Überprüfung von starken Namen für vollständig vertrauenswürdige Assemblys umgangen werden soll, die in eine vollständige Vertrauenswürdigkeit geladen werden <xref:System.AppDomain> .

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<bypassTrustedAppStrongNames>**

## <a name="syntax"></a>Syntax

```xml
<bypassTrustedAppStrongNames
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob das Umgehungs Feature aktiviert ist, das das Validieren starker Namen für vollständig vertrauenswürdige Assemblys vermeidet. Wenn diese Funktion aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft, wenn die Assembly geladen wird. Der Standardwert lautet `true`.|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|BESCHREIBUNG|
|-----------|-----------------|
|`true`|Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden nicht überprüft, wenn die Assemblys in eine voll vertrauenswürdige Assembly geladen werden <xref:System.AppDomain> . Dies ist die Standardeinstellung.|
|`false`|Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in eine voll vertrauenswürdige Assembly geladen werden <xref:System.AppDomain> . Die Signatur des starken Namens wird nur zur Richtigkeit der Signatur geprüft. Er wird nicht mit einem anderen starken Namen für eine Entsprechung verglichen.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|

## <a name="remarks"></a>Bemerkungen

Die Strong-Name-Bypass-Funktion vermeidet den Aufwand der Signatur Überprüfung mit starkem Namen für vollständig vertrauenswürdige Assemblys.

Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:

- Voll vertrauenswürdig ohne den <xref:System.Security.Policy.StrongName> Beweis (z. b `MyComputer` . hat einen Zonen Nachweis).

- Geladen in eine voll vertrauenswürdige <xref:System.AppDomain>

- Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain>

- Nicht verzögert signiert

> [!NOTE]
> Wenn das Umgehungs Feature für alle Anwendungen auf dem Computer mithilfe eines Registrierungsschlüssels ausgeschaltet wurde, hat diese Einstellung keine Auswirkungen. Weitere Informationen finden Sie unter Gewusst [wie: Deaktivieren des Strong-Name-Bypass-Features](../../../../standard/assembly/disable-strong-name-bypass-feature.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie das Verhalten angegeben wird, mit dem die Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys überprüft wird.

```xml
<configuration>
   <runtime>
      <bypassTrustedAppStrongNames enabled="false"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [How to: Deaktivieren des Features zur Umgehung von starken Namen](../../../../standard/assembly/disable-strong-name-bypass-feature.md)
