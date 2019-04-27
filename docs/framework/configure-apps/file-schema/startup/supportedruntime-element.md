---
title: <supportedRuntime> Konfigurationselement – .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: 2b0bce015216c2eaf2c35aee2d9174f109dff16e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673912"
---
# <a name="supportedruntime-element"></a>\<< SupportedRuntime >-Element

Gibt an, welche Version der common Language Runtime und, optional, .NET Framework-Version der Anwendung unterstützt.  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<startup>](../startup/startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a>Syntax

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Attribute

|Attribut|Beschreibung|
|---------------|-----------------|
|**version**|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die Version der Common Language Runtime (CLR) angibt, die diese Anwendung unterstützt. Für gültige Werte für die `version` Attribut, finden Sie unter den ["RuntimeVersion"-Werte](#version) Abschnitt. **Hinweis**:  Über die .NET Framework 3.5 die "*Laufzeitversion*" Wert hat das Format *wichtigen*. *kleinere*. *Erstellen Sie*. Beginnend mit [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] sind nur die Haupt- und Nebenversionsnummern erforderlich (d. h. "v4.0" anstelle von "v4.0.30319"). Die kürzere Zeichenfolge wird empfohlen.|
|**sku**|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die SKU (Stock Keeping Unit) angibt, die wiederum angibt, welches .NET Framework-Release von dieser Anwendung unterstützt wird.<br /><br /> Beginnend mit .NET Framework 4.0 wird die Verwendung des `sku`-Attributs empfohlen.  Wenn vorhanden, gibt es die Version des .NET Frameworks an, auf die die App aufgerichtet ist.<br /><br /> Gültige Werte des Sku-Attributs finden Sie in der ["Sku Id"-Werte](#sku) Abschnitt.|

## <a name="remarks"></a>Hinweise

Wenn die  **\<SupportedRuntime >** Element ist nicht vorhanden ist, in der Konfigurationsdatei der Anwendung, die Version der Laufzeit verwendet, die zum Erstellen der Anwendung verwendet wird.

Die  **\<SupportedRuntime >** Element sollte verwendet werden, von allen Anwendungen, die mit Version 1.1 oder höher der Runtime erstellt. Anwendungen, die nur in Version 1.0 von der Laufzeit nicht verwenden, müssen die [ \<RequiredRuntime >](../startup/requiredruntime-element.md) Element.

> [!NOTE]
> Bei Verwendung der [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) Funktion, um die Konfigurationsdatei angeben, müssen Sie die `<requiredRuntime>` -Element für alle Versionen der Laufzeit. Die `<supportedRuntime>` Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md).  
  
Bei Apps, die Versionen der Laufzeit aus .NET Framework 1.1 bis 3.5 unterstützen, sollte, wenn mehrere Versionen der Laufzeit unterstützt werden, das erste Element die bevorzugte Version der Laufzeit angeben, und das letzte die am wenigsten bevorzugte Version. Für apps, die .NET Framework 4.0 oder höhere Versionen unterstützen, die `version` -Attribut gibt an, die CLR-Version, die für die .NET Framework 4 und höher ist, und die `sku` -Attribut gibt an, die einzelnen .NET Framework-Version, die die App ausgerichtet ist. 

Wenn die  **\<SupportedRuntime >** -Element mit dem `sku` Attribut in der Konfigurationsdatei vorhanden ist und die installierte .NET Framework-Version wird unten und klicken Sie dann die angegebenen unterstützte Version der Anwendung nicht ausgeführt werden, sondern zeigt stattdessen eine Meldung gefragt werden, um die unterstützte Version zu installieren. Andernfalls wird die Anwendung versucht, die auf alle installierten Version ausgeführt werden, aber es kann unerwartet Verhalten, wenn er nicht vollständig kompatibel mit dieser Version ist. (Kompatibilitätsunterschiede zwischen Versionen von .NET Framework, finden Sie unter [der Anwendungskompatibilität in .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Aus diesem Grund empfehlen wir, dass Sie dieses Element in der Konfigurationsdatei der Anwendung für die Fehlerdiagnose von einfacher enthalten. (Die Konfigurationsdatei von Visual Studio automatisch generiert, wenn es bereits ein neues Projekt erstellen enthält.)
  
> [!NOTE]
> Wenn Ihre Anwendung legacy-Aktivierungspfade, z. B. verwendet die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten diese Pfade Version 4 der CLR anstelle von einer früheren Version aktivieren, oder wenn Ihre Anwendung, mit der erstelltwird[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]aber eine Abhängigkeit auf eine Assembly im gemischten Modus mit einer früheren Version von .NET Framework erstellt es genügt nicht an die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in der Liste der unterstützten Laufzeiten. Darüber hinaus werden in der [ \<Startup > Element](../startup/startup-element.md) in der Konfigurationsdatei müssen Sie festlegen der `useLegacyV2RuntimeActivationPolicy` Attribut `true`. Wenn jedoch dieses Attribut auf `true` festgelegt ist, werden alle Komponenten, die mit früheren Versionen von .NET Framework erstellt wurden, mit [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] ausgeführt statt den Laufzeiten, mit denen sie erstellt wurden.

Es wird empfohlen, dass Sie die Anwendungen mit allen .NET Framework-Versionen testen, in denen sie ausgeführt werden können.

<a name="version"></a> 
## <a name="runtime-version-values"></a>„runtime version“-Werte
Die `runtime` Attribut gibt an, die Common Language Runtime (CLR)-Version, die für eine bestimmte Anwendung erforderlich ist. Beachten Sie, die alle .NET Framework 4.x-Versionen angeben der `v4.0` CLR. Die folgende Tabelle enthält die gültigen Werte für die *Laufzeitversion* Wert, der die `version` Attribut.

|.NET Framework-Version|`version` Attribut|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3.5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku"></a> "Sku Id"-Werte

Die `sku` Attribut einen Zielframework-Moniker (TFM) verwendet, um die Version von .NET Framework anzugeben, die die app ausgerichtet ist und zum Ausführen benötigt. Die folgende Tabelle enthält die gültigen Werte, die von Microsoft Intune die `sku` -Attribut, beginnend mit .NET Framework 4.

|.NET Framework-Version|`sku` Attribut|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Clientprofil|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, Plattformupdate 1|".NETFramework,Version=v4.0.1"|
|4.0, Clientprofil, Update 1|". NETFramework, Version 4.0.1, Profil = = Client "|
|4.0, Plattformupdate 2|".NETFramework,Version=v4.0.2"|
|4.0, Clientprofil, Update 2|". NETFramework, Version = V4.0.2, Profil = Client "|
|4.0, Plattformupdate 3|".NETFramework,Version=v4.0.3"|
|4.0, Clientprofil, Update 3|". NETFramework, Version = Verze 4.0.3, Profil = Client "|
|4.5|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|".NETFramework,Version=v4.6.2"|
|4.7|".NETFramework,Version=v4.7"|
|4.7.1|".NETFramework,Version=v4.7.1"|
|4.7.2|".NETFramework,Version=v4.7.2"|
|4.8|".NETFramework,Version=v4.8"|

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht, wie Sie die unterstützte Laufzeitversion in einer Konfigurationsdatei angeben. Die Konfigurationsdatei gibt an, dass die app auf .NET Framework 4.7 ausgerichtet ist.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei verwendet werden.

## <a name="see-also"></a>Siehe auch

- [Startup Settings Schema (Schema für Starteinstellungen)](../startup/index.md)
- [Konfigurationsdateischema](../index.md)
- [Prozessinterne parallele Ausführung](../../../deployment/in-process-side-by-side-execution.md)