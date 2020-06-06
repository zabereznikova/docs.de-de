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
ms.openlocfilehash: fe96673b95f48cb75d36662a680bf56a59363f9f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "71697490"
---
# <a name="requiredruntime-element"></a>\<requiredRuntime>-Element

Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt. Dieses Element ist veraltet und sollte nicht mehr verwendet werden. [`supportedRuntime`](supportedruntime-element.md)Stattdessen sollte das-Element verwendet werden.

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<startup>**](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<requiredRuntime>**  

## <a name="syntax"></a>Syntax

```xml
   <requiredRuntime  
version="runtime version"
safemode="true|false"/>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.

### <a name="attributes"></a>Attribute

|attribute|BESCHREIBUNG|
|---------------|-----------------|
|`version`|Optionales Attribut.<br /><br /> Ein Zeichen folgen Wert, der die Version der .NET Framework angibt, die von dieser Anwendung unterstützt wird. Der Zeichen folgen Wert muss mit dem Verzeichnisnamen unter dem Stammverzeichnis der .NET Framework Installation identisch sein. Der Inhalt des Zeichen folgen Werts wird nicht analysiert.|
|`safemode`|Optionales Attribut.<br /><br /> Gibt an, ob der Startcode der Laufzeit die Registrierung durchsucht, um die Laufzeitversion zu bestimmen.|

## <a name="safemode-attribute"></a>safemode-Attribut

|Wert|BESCHREIBUNG|
|-----------|-----------------|
|`false`|Der Startcode der Laufzeit sucht in der Registrierung. Dies ist der Standardwert.|
|`true`|Der Startcode der Laufzeit sucht nicht in der Registrierung.|

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|
|`startup`|Enthält das- `<requiredRuntime>` Element.|

## <a name="remarks"></a>Bemerkungen
 Anwendungen, die zur Unterstützung von nur Version 1,0 der Laufzeit erstellt wurden, müssen das- `<requiredRuntime>` Element verwenden. Anwendungen, die mit Version 1,1 oder höher der Laufzeit erstellt wurden, müssen das- `<supportedRuntime>` Element verwenden.

> [!NOTE]
> Wenn Sie die [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) -Funktion verwenden, um die Konfigurationsdatei anzugeben, müssen Sie das- `<requiredRuntime>` Element für alle Versionen der Common Language Runtime verwenden. Das- `<supportedRuntime>` Element wird ignoriert, wenn Sie [corbindtoriuntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)verwenden.

 Die `version` Attribut Zeichenfolge muss mit dem Namen des Installations Ordners für die angegebene Version der .NET Framework identisch sein. Diese Zeichenfolge wird nicht interpretiert. Wenn der Startcode der Laufzeit keinen übereinstimmenden Ordner findet, wird die Laufzeit nicht geladen. der Startcode zeigt eine Fehlermeldung an und beendet den Vorgang.

> [!NOTE]
> Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert das- `<requiredRuntime>` Element.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie die Laufzeitversion in einer Konfigurationsdatei angegeben wird.

```xml
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Schema für Starteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [How to: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
