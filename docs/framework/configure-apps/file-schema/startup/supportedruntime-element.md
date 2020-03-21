---
title: <supportedRuntime>Konfigurationselement - .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: e16eb098db4bce115a5f1e043829eb272c952860
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153697"
---
# <a name="supportedruntime-element"></a>\<unterstützteruntime>-Element

Gibt an, welche Common Language-Laufzeitversion und optional .NET Framework-Version von der Anwendung unterstützt wird.  

[\<Konfiguration>](../configuration-element.md)  
&nbsp;&nbsp;[\<Startup->](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<unterstützteRuntime->**  

## <a name="syntax"></a>Syntax

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Attributes

|attribute|Beschreibung|
|---------------|-----------------|
|**version**|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die Version der Common Language Runtime (CLR) angibt, die diese Anwendung unterstützt. Gültige Werte des `version` Attributs finden Sie im Abschnitt ["Laufzeitversion"-Werte.](#version) **Hinweis:**  Über .NET Framework 3.5 nimmt der Wert "*Laufzeitversion*" die Form *major*an. *moll*. *erstellen*. Ab .NET Framework 4 sind nur die Haupt- und Nebenversionsnummern erforderlich (d. h. "v4.0" anstelle von "v4.0.30319"). Die kürzere Zeichenfolge wird empfohlen.|
|**Sku**|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die SKU (Stock Keeping Unit) angibt, die wiederum angibt, welches .NET Framework-Release von dieser Anwendung unterstützt wird.<br /><br /> Beginnend mit .NET Framework 4.0 wird die Verwendung des `sku`-Attributs empfohlen.  Wenn vorhanden, gibt es die Version des .NET Frameworks an, auf die die App aufgerichtet ist.<br /><br /> Gültige Werte des sku-Attributs finden Sie im Abschnitt ["sku id" werte.](#sku)|

## <a name="remarks"></a>Bemerkungen

Wenn das ** \<unterstützteRuntime->-Element** in der Anwendungskonfigurationsdatei nicht vorhanden ist, wird die Version der Laufzeit verwendet, die zum Erstellen der Anwendung verwendet wird.

Das ** \<unterstützteRuntime->-Element** sollte von allen Anwendungen verwendet werden, die mit Version 1.1 oder höher der Laufzeit erstellt wurden. Anwendungen, die nur Version 1.0 der Laufzeit unterstützen, müssen das [ \<erforderlicheRuntime->-Element](../startup/requiredruntime-element.md) verwenden.

> [!NOTE]
> Wenn Sie die [Funktion CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) verwenden, um die `<requiredRuntime>` Konfigurationsdatei anzugeben, müssen Sie das Element für alle Versionen der Laufzeit verwenden. Das `<supportedRuntime>` Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)verwenden.  
  
Bei Apps, die Versionen der Laufzeit aus .NET Framework 1.1 bis 3.5 unterstützen, sollte, wenn mehrere Versionen der Laufzeit unterstützt werden, das erste Element die bevorzugte Version der Laufzeit angeben, und das letzte die am wenigsten bevorzugte Version. Bei Apps, die die Versionen von .NET `version` Framework 4.0 oder höher unterstützen, gibt das Attribut die CLR-Version an, die für die .NET Framework 4- und höher-Versionen gemeinsam ist, und das `sku` Attribut gibt die einzelne .NET Framework-Version an, auf die die App abzielt.

Wenn das ** \<unterstützteRuntime->-Element** mit dem `sku` Attribut in der Konfigurationsdatei vorhanden ist und die installierte .NET Framework-Version niedriger als die angegebene unterstützte Version ist, kann die Anwendung nicht ausgeführt werden und zeigt stattdessen eine Meldung an, in der die Installation der unterstützten Version gefordert wird. Andernfalls versucht die Anwendung, auf jeder installierten Version ausgeführt zu werden, verhält sich jedoch möglicherweise unerwartet, wenn sie nicht vollständig mit dieser Version kompatibel ist. (Kompatibilitätsunterschiede zwischen Versionen von .NET Framework finden Sie [unter Anwendungskompatibilität in .NET Framework](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility).) Daher wird empfohlen, dieses Element in die Anwendungskonfigurationsdatei aufzunehmen, um die Fehlerdiagnose zu vereinfachen. (Die Konfigurationsdatei, die beim Erstellen eines neuen Projekts automatisch von Visual Studio generiert wird, enthält sie bereits.)
  
> [!NOTE]
> Wenn Ihre Anwendung ältere Aktivierungspfade verwendet, z. B. die [CorBindToRuntimetimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten, dass diese Pfade Version 4 der CLR anstelle einer früheren Version aktivieren, oder wenn Ihre Anwendung mit .NET Framework 4 erstellt wird, aber von einer Assembly im gemischten Modus abhängig ist, die mit einer früheren Version von .NET Framework erstellt wurde, reicht es nicht aus, das .NET Framework 4 in der Liste der unterstützten Laufzeiten anzugeben. Darüber hinaus müssen Sie im [ \<Start>-Element](../startup/startup-element.md) in `useLegacyV2RuntimeActivationPolicy` der `true`Konfigurationsdatei das Attribut auf festlegen. Wenn Sie dieses `true` Attribut jedoch so festlegen, dass alle Komponenten, die mit früheren Versionen von .NET Framework erstellt wurden, mit .NET Framework 4 anstelle der Laufzeiten ausgeführt werden, mit denen sie erstellt wurden.

Es wird empfohlen, dass Sie die Anwendungen mit allen .NET Framework-Versionen testen, in denen sie ausgeführt werden können.

<a name="version"></a>
## <a name="runtime-version-values"></a>„runtime version“-Werte
Das `runtime` Attribut gibt die CLR-Version (Common Language Runtime) an, die für eine bestimmte Anwendung erforderlich ist. Beachten Sie, dass alle .NET Framework `v4.0` v4.x-Versionen die CLR angeben. In der folgenden Tabelle sind gültige Werte `version` für den *Laufzeitversionswert* des Attributs aufgeführt.

|.NET Framework-Version|`version`-Attribut|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3,5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku-id-values"></a><a name="sku"></a>"sku id"-Werte

Das `sku` Attribut verwendet einen Zielframeworkmoniker (TFM), um die Version von .NET Framework anzugeben, auf die die App abzielt und ausgeführt werden muss. In der folgenden Tabelle sind gültige `sku` Werte aufgeführt, die vom Attribut unterstützt werden, beginnend mit .NET Framework 4.

|.NET Framework-Version|`sku`-Attribut|
|----------------------------|---------------------|
|4,0|".NETFramework,Version=v4.0"|
|4.0, Clientprofil|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, Plattformupdate 1|". NETFramework,Version=v4.0.1"|
|4.0, Clientprofil, Update 1|". NETFramework,Version=v4.0.1,Profil=Client"|
|4.0, Plattformupdate 2|". NETFramework,Version=v4.0.2"|
|4.0, Clientprofil, Update 2|". NETFramework,Version=v4.0.2,Profil=Client"|
|4.0, Plattformupdate 3|". NETFramework,Version=v4.0.3"|
|4.0, Clientprofil, Update 3|". NETFramework,Version=v4.0.3,Profil=Client"|
|4,5|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". NETFramework,Version=v4.6.2"|
|4,7|". NETFramework,Version=v4.7"|
|4.7.1|". NETFramework,Version=v4.7.1"|
|4.7.2|". NETFramework,Version=v4.7.2"|
|4.8|". NETFramework,Version=v4.8"|

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht, wie Sie die unterstützte Laufzeitversion in einer Konfigurationsdatei angeben. Die Konfigurationsdatei gibt an, dass die App auf .NET Framework 4.7 abzielt.

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungskonfigurationsdatei verwendet werden.

## <a name="see-also"></a>Weitere Informationen

- [Starteinstellungsschema](../startup/index.md)
- [Schema der Konfigurationsdatei](../index.md)
- [Prozessinterne parallele Ausführung](../../../deployment/in-process-side-by-side-execution.md)
