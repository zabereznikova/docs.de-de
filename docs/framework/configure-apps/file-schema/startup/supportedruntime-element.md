---
title: <supportedRuntime> Configuration-Element-.net
ms.date: 04/02/2019
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: 79b49cbc9b122e6591d07643a341841b262edff4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201706"
---
# <a name="supportedruntime-element"></a>\<supportedRuntime>-Element

Gibt an, welche Common Language Runtime Version und optional .NET Framework Version von der Anwendung unterstützt werden.  

[\<configuration>](../configuration-element.md)  
&nbsp;&nbsp;[\<startup>](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<supportedRuntime>**  

## <a name="syntax"></a>Syntax

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>Attribute

|attribute|Beschreibung|
|---------------|-----------------|
|**version**|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die Version der Common Language Runtime (CLR) angibt, die diese Anwendung unterstützt. Gültige Werte des- `version` Attributs finden Sie im Abschnitt ["Lauf Zeit Versions Werte"](#version) . **Hinweis:**  Über den .NET Framework 3,5 hat der Wert für die*Laufzeitversion*das Format *Major*. *neben*Version. *Erstellen*Sie. Ab .NET Framework 4 sind nur die Haupt-und neben Versionsnummern erforderlich (d. h. "v 4.0" anstelle von "v 4.0.30319"). Die kürzere Zeichenfolge wird empfohlen.|
|**sku**|Optionales Attribut.<br /><br /> Ein Zeichenfolgenwert, der die SKU (Stock Keeping Unit) angibt, die wiederum angibt, welches .NET Framework-Release von dieser Anwendung unterstützt wird.<br /><br /> Beginnend mit .NET Framework 4.0 wird die Verwendung des `sku`-Attributs empfohlen.  Wenn vorhanden, gibt es die Version des .NET Frameworks an, auf die die App aufgerichtet ist.<br /><br /> Gültige Werte des SKU-Attributs finden Sie im Abschnitt ["SKU-ID"-Werte](#sku) .|

## <a name="remarks"></a>Bemerkungen

Wenn das- **\<supportedRuntime>** Element in der Anwendungs Konfigurationsdatei nicht vorhanden ist, wird die Version der Laufzeit verwendet, die zum Erstellen der Anwendung verwendet wird.

Das- **\<supportedRuntime>** Element sollte von allen Anwendungen verwendet werden, die mit Version 1,1 oder höher der Laufzeit erstellt wurden. Anwendungen, die zur Unterstützung von nur Version 1,0 der Laufzeit erstellt wurden, müssen das- [\<requiredRuntime>](requiredruntime-element.md) Element verwenden.

> [!NOTE]
> Wenn Sie die [CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md) -Funktion verwenden, um die Konfigurationsdatei anzugeben, müssen Sie das- `<requiredRuntime>` Element für alle Versionen der Common Language Runtime verwenden. Das- `<supportedRuntime>` Element wird ignoriert, wenn Sie [corbindtoriuntimebycfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)verwenden.  
  
Bei Apps, die Versionen der Laufzeit aus .NET Framework 1.1 bis 3.5 unterstützen, sollte, wenn mehrere Versionen der Laufzeit unterstützt werden, das erste Element die bevorzugte Version der Laufzeit angeben, und das letzte die am wenigsten bevorzugte Version. Für apps, die den .NET Framework 4,0 oder höhere Versionen unterstützen, gibt das- `version` Attribut die CLR-Version an, die für die .NET Framework 4 und höhere Versionen gilt, und das- `sku` Attribut gibt die einzelne .NET Framework Version an, auf die die APP abzielt.

Wenn das **\<supportedRuntime>** Element mit dem `sku` -Attribut in der Konfigurationsdatei vorhanden ist und die installierte .NET Framework Version niedriger ist als die angegebene unterstützte Version, kann die Anwendung nicht ausgeführt werden und zeigt stattdessen eine Meldung an, in der Sie aufgefordert werden, die unterstützte Version zu installieren. Andernfalls versucht die Anwendung, auf einer beliebigen installierten Version auszuführen. Sie verhält sich jedoch möglicherweise unerwartet, wenn Sie mit dieser Version nicht vollständig kompatibel ist. (Informationen zu Kompatibilitäts unterschieden zwischen den Versionen von .NET Framework finden Sie unter [Anwendungs Kompatibilität in der .NET Framework](../../../migration-guide/application-compatibility.md).) Daher wird empfohlen, dass Sie dieses Element in die Anwendungs Konfigurationsdatei einschließen, um die Fehlerdiagnose zu vereinfachen. (Die Konfigurationsdatei, die automatisch von Visual Studio generiert wird, wenn ein neues Projekt erstellt wird, ist bereits enthalten.)
  
> [!NOTE]
> Wenn Ihre Anwendung ältere Aktivierungs Pfade verwendet, beispielsweise die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten, dass diese Pfade Version 4 der CLR anstelle einer früheren Version aktivieren, oder wenn die Anwendung mit dem .NET Framework 4 erstellt wurde, aber eine Abhängigkeit von einer Assembly mit gemischtem Modus hat, die mit einer früheren Version der .NET Framework erstellt wurde .NET Framework Außerdem müssen Sie im- [ \<startup> Element](startup-element.md) in der Konfigurationsdatei das- `useLegacyV2RuntimeActivationPolicy` Attribut auf festlegen `true` . Wenn dieses Attribut auf festgelegt wird, bedeutet dies, `true` dass alle Komponenten, die mit früheren Versionen der .NET Framework erstellt wurden, anstelle der Laufzeiten, mit denen Sie erstellt wurden, mit dem .NET Framework 4 ausgeführt werden.

Es wird empfohlen, dass Sie die Anwendungen mit allen .NET Framework-Versionen testen, in denen sie ausgeführt werden können.

<a name="version"></a>

## <a name="runtime-version-values"></a>„runtime version“-Werte

Das- `runtime` Attribut gibt die CLR-Version (Common Language Runtime) an, die für eine bestimmte Anwendung erforderlich ist. Beachten Sie, dass alle .NET Framework v4. x-Versionen die `v4.0` CLR angeben. In der folgenden Tabelle sind gültige Werte für den *Lauf Zeit Versions* Wert des- `version` Attributs aufgeführt.

|.NET Framework-Version|`version`-Attribut|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3,5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku-id-values"></a><a name="sku"></a> SKU-ID-Werte

Das- `sku` Attribut verwendet einen zielframeworkmoniker (TFM), um die Version der .NET Framework anzugeben, die die APP als Ziel hat und für die Ausführung erforderlich ist. In der folgenden Tabelle werden die gültigen Werte aufgelistet, die vom-Attribut unterstützt werden `sku` , beginnend mit dem .NET Framework 4.

|.NET Framework-Version|`sku`-Attribut|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0, Clientprofil|".NETFramework,Version=v4.0,Profile=Client"|
|4.0, Plattformupdate 1|". NETFramework, Version = v 4.0.1 "|
|4.0, Clientprofil, Update 1|". NETFramework, Version = v 4.0.1, Profile = Client "|
|4.0, Plattformupdate 2|". NETFramework, Version = v 4.0.2 "|
|4.0, Clientprofil, Update 2|". NETFramework, Version = v 4.0.2, Profile = Client "|
|4.0, Plattformupdate 3|". NETFramework, Version = v 4.0.3 "|
|4.0, Clientprofil, Update 3|". NETFramework, Version = v 4.0.3, Profile = Client "|
|4.5|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5.1"|
|4.5.2|".NETFramework,Version=v4.5.2"|
|4.6|".NETFramework,Version=v4.6"|
|4.6.1|".NETFramework,Version=v4.6.1"|
|4.6.2|". NETFramework, Version = v 4.6.2 "|
|4.7|". NETFramework, Version = v 4.7 "|
|4.7.1|". NETFramework, Version = v 4.7.1 "|
|4.7.2|". NETFramework, Version = v 4.7.2 "|
|4.8|". NETFramework, Version = v 4.8 "|

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht, wie Sie die unterstützte Laufzeitversion in einer Konfigurationsdatei angeben. Die Konfigurationsdatei gibt an, dass die APP auf den .NET Framework 4,7 abzielt.

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

- [Schema für Start Einstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Prozessinterne parallele Ausführung](../../../deployment/in-process-side-by-side-execution.md)
