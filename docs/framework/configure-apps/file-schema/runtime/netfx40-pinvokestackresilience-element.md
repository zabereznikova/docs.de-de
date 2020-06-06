---
title: <NetFx40_PInvokeStackResilience>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116161"
---
# <a name="netfx40_pinvokestackresilience-element"></a>\<NetFx40_PInvokeStackResilience>-Element

Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a>Syntax

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit falsche Platt Form Aufruf Deklarationen erkennt und den Stapel zur Laufzeit auf 32-Bit-Plattformen automatisch korrigiert.|

## <a name="enabled-attribute"></a>Enabled-Attribut

|Wert|BESCHREIBUNG|
|-----------|-----------------|
|`0`|Die Laufzeit verwendet die schnellere Interop-marshallingarchitektur, die in der .NET Framework 4 eingeführt wurde, die falsche Platt Form Aufruf Deklarationen nicht erkennt und repariert. Dies ist die Standardeinstellung.|
|`1`|Die Laufzeit verwendet langsamere Übergänge, die falsche Platt Form Aufruf Deklarationen erkennen und beheben.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|

## <a name="remarks"></a>Bemerkungen

Mit diesem Element können Sie ein schnelleres Interop-Marshalling für die Lauf Zeit Resilienz gegen falsche Platt Form Aufruf Deklarationen durchführen.

Ab .NET Framework 4 bietet eine optimierte Interop-marshallingarchitektur eine bedeutende Leistungsverbesserung bei Übergängen von verwaltetem Code zu nicht verwaltetem Code. In früheren Versionen der .NET Framework erkannte die Marshallingschicht falsche Platt Form Aufruf Deklarationen auf 32-Bit-Plattformen und hat den Stapel automatisch korrigiert. In der neuen marshallingarchitektur ist dieser Schritt ausgeschlossen. Folglich sind Übergänge sehr schnell, aber eine falsche Platt Form Aufruf Deklaration kann einen Programmfehler verursachen.

Um das erkennen falscher Deklarationen während der Entwicklung zu vereinfachen, wurde die Visual Studio-debuggingdarstellung verbessert. Der [pinvokestackungleichsverwaltungs](../../../debug-trace-profile/pinvokestackimbalance-mda.md) -Assistent für verwaltetes Debuggen (MDA) benachrichtigt Sie über falsche Platt Form Aufruf Deklarationen, wenn die Anwendung mit dem angefügten Debugger ausgeführt wird.

Sie können das-Element verwenden, um Szenarios zu behandeln, in denen Ihre Anwendung Komponenten verwendet, die Sie nicht neu kompilieren können und falsche Platt Form Aufruf Deklarationen aufweisen `NetFx40_PInvokeStackResilience` . Wenn Sie dieses Element der Anwendungs Konfigurationsdatei mit `enabled="1"` opts in einen Kompatibilitätsmodus mit dem Verhalten früherer Versionen der .NET Framework hinzufügen, wird dies zu langsameren Übergängen. Assemblys, die mit früheren Versionen der .NET Framework kompiliert wurden, werden automatisch in diesen Kompatibilitätsmodus gewählt und benötigen dieses Element nicht.

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie die Resilienz gegenüber falschen Platt Form Aufruf Deklarationen für eine Anwendung verbessert werden kann, was zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code geführt hat.

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
