---
title: <requiredRuntime>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: f5a9f99133c153401694372abaeea10a02e492e5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634191"
---
# <a name="requiredruntime-element"></a>\<RequiredRuntime >-Element

Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt. Dieses Element ist veraltet und sollte nicht mehr verwendet werden. Die [ `supportedRuntime` ](supportedruntime-element.md) Element sollte stattdessen verwendet werden.

\<configuration> \<startup> \<requiredRuntime>

## <a name="syntax"></a>Syntax

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|`version`|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der angibt, die Version von .NET Framework, die diese Anwendung unterstützt. Der Zeichenfolgenwert muss den Namen des Verzeichnisses finden Sie unter dem Stamm der .NET Framework-Installation übereinstimmen. Der Inhalt des Zeichenfolgenwerts wird nicht analysiert.|
|`safemode`|Optionales Attribut.<br /><br /> Gibt an, ob die Common Language Runtime-Startcode die Registrierung zum Ermitteln der RuntimeVersion der Common Language durchsucht.|

## <a name="safemode-attribute"></a>Safemode-Attribut

|Wert|Beschreibung|
|-----------|-----------------|
|`false`|Der Startcode für die Common Language Runtime sucht in der Registrierung. Dies ist der Standardwert.|
|`true`|Der Laufzeitstartcode scheint sich nicht in der Registrierung.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`startup`|Enthält die `<requiredRuntime>` Element.|

## <a name="remarks"></a>Hinweise
 Anwendungen, die nur in Version 1.0 von der Laufzeit nicht verwenden, müssen die `<requiredRuntime>` Element. Erstellen von Anwendungen mit Version 1.1 oder höher der Runtime verwenden, müssen die `<supportedRuntime>` Element.

> [!NOTE]
> Bei Verwendung der [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) Funktion, um die Konfigurationsdatei angeben, müssen Sie die `<requiredRuntime>` -Element für alle Versionen der Laufzeit. Die `<supportedRuntime>` Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).

 Die `version` Attributzeichenfolge muss den Ordnernamen Installation, für die angegebene Version von .NET Framework entsprechen. Diese Zeichenfolge wird nicht interpretiert. Wenn der Laufzeitstartcode einen entsprechenden Ordner nicht gefunden wird, ist die Runtime nicht geladen werden. der Startcode zeigt eine Fehlermeldung an und wird beendet.

> [!NOTE]
> Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert der `<requiredRuntime>` Element.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie die Runtime-Version in einer Konfigurationsdatei angegeben wird.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Startup Settings Schema (Schema für Starteinstellungen)](index.md)
- [Konfigurationsdateischema](../index.md)
- [Vorgehensweise: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
