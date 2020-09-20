---
title: Kürzungsoptionen
description: Hier erfahren Sie, wie Sie die Kürzung von eigenständigen Apps steuern.
author: sbomer
ms.author: svbomer
ms.date: 08/25/2020
ms.openlocfilehash: 89bd195a97c2f1bbbba9199fea51c917c4e4836b
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515831"
---
# <a name="trimming-options"></a>Kürzungsoptionen

Die folgenden MSBuild-Eigenschaften und -Elemente beeinflussen das Verhalten von [gekürzten eigenständigen Bereitstellungen](trim-self-contained.md). Im Zusammenhang mit einigen Optionen wird `ILLink` erwähnt. Dies ist der Name des zugrunde liegenden Tools, das die Kürzung implementiert. Weitere Informationen zum zugrunde liegenden Tool finden Sie in der [Linker-Dokumentation](https://github.com/mono/linker/tree/master/docs).

## <a name="enable-trimming"></a>Aktivieren der Kürzung

- `<PublishTrimmed>true</PublishTrimmed>`

   Aktivieren Sie die Kürzung während der Veröffentlichung mit den Standardeinstellungen, die vom SDK definiert werden.

Wenn Sie `Microsoft.NET.Sdk` verwenden, wird eine Kürzung der Frameworkassemblys aus dem netcoreapp-Runtimepaket auf Assemblyebene durchgeführt. Anwendungscode und Bibliotheken ohne Framework werden nicht gekürzt. Andere SDKs definieren möglicherweise andere Standardwerte.

## <a name="trimming-granularity"></a>Kürzungsgranularität

Die folgenden Granularitätseinstellungen steuern, wie aggressiv nicht verwendete IL verworfen wird. Dies kann als Eigenschaft oder als Metadaten für eine [einzelne Assembly](#trimmed-assemblies) festgelegt werden.

- `<TrimMode>copyused</TrimMode>`

   Aktivieren Sie das Kürzen auf Assemblyebene, wodurch die gesamte Assembly erhalten bleibt, wenn ein beliebiger Teil davon verwendet wird (im statischen Kontext).

- `<TrimMode>link</TrimMode>`

    Aktivieren Sie die Kürzung auf Memberebene, wodurch nicht verwendete Member aus Typen entfernt werden.

Assemblys mit den Metadaten `<IsTrimmable>true</IsTrimmable>`, aber ohne expliziten `TrimMode`, verwenden den globalen `TrimMode`. Der Standard-`TrimMode` für `Microsoft.NET.Sdk` ist `copyused`.

## <a name="trimmed-assemblies"></a>Gekürzte Assemblys

Beim Veröffentlichen einer gekürzten App berechnet das SDK ein `ItemGroup`-Element namens `ManagedAssemblyToLink`, das die Dateien darstellt, die für die Kürzung verarbeitet werden sollen. `ManagedAssemblyToLink` kann über Metadaten verfügen, die das Kürzungsverhalten pro Assembly steuern. Erstellen Sie ein Ziel, das vor dem integrierten `PrepareForILLink`-Ziel ausgeführt wird, um diese Metadaten festzulegen. Das folgende Beispiel zeigt, wie Sie das Kürzen von `MyAssembly` aktivieren.

```xml
<Target Name="ConfigureTrimming"
        BeforeTargets="PrepareForILLink">
  <ItemGroup>
    <ManagedAssemblyToLink Condition="'%(Filename)' == 'MyAssembly'">
      <IsTrimmable>true</IsTrimmable>
    </ManagedAssemblyToLink>
  </ItemGroup>
</Target>
```

Fügen Sie `ManagedAssemblyToLink` keine Elemente hinzu, oder entfernen Sie keine Elemente, da das SDK diese Gruppe während der Veröffentlichung berechnet und davon ausgeht, dass nichts geändert wird. Folgende Metadaten werden unterstützt:

- `<IsTrimmable>true</IsTrimmable>`

  Hiermit wird gesteuert, ob die angegebene Assembly gekürzt wird.

- `<TrimMode>copyused</TrimMode>` oder `<TrimMode>link</TrimMode>`

  Hiermit wird die [Kürzungsgranularität](#trimming-granularity) dieser Assembly gesteuert. Diese hat Vorrang vor dem globalen `TrimMode`. Das Festlegen von `TrimMode` für eine Assembly impliziert `<IsTrimmable>true</IsTrimmable>`.

## <a name="root-assemblies"></a>Stammassemblys

Alle Assemblys, die `<IsTrimmable>true</IsTrimmable>` nicht aufweisen, werden als Stämme für die Analyse angesehen. Das bedeutet, dass sie und alle statisch verstandenen Abhängigkeiten beibehalten werden. Zusätzliche Assemblys können je nach Name zu Stammassemblys werden (ohne die Erweiterung `.dll`):

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="MyAssembly" />
</ItemGroup>
```

## <a name="root-descriptors"></a>Stammdeskriptoren

Eine andere Möglichkeit zum Angeben von Stämmen für die Analyse ist die Verwendung einer XML-Datei, die den Linker für das [Deskriptorformat](https://github.com/mono/linker/blob/master/docs/data-formats.md#descriptor-format) verwendet. Dies ermöglicht es Ihnen, bestimmte Member anstelle einer ganzen Assembly zu verwenden.

```xml
<ItemGroup>
  <TrimmerRootDescriptor Include="MyRoots.xml" />
</ItemGroup>
```

Beispielsweise kann `MyRoots.xml` eine bestimmte Methode sein, auf die die Anwendung dynamisch zugreift:

```xml
<linker>
  <assembly fullname="MyAssembly">
    <type fullname="MyAssembly.MyClass">
      <method name="DynamicallyAccessedMethod" />
    </type>
  </assembly>
</linker>
```

## <a name="analysis-warnings"></a>Analysewarnungen

Durch die Kürzung wird die IL entfernt, die statisch nicht erreichbar ist. Apps, die Reflexion oder andere Muster verwenden, die die dynamischen Abhängigkeiten erstellen, können durch das Kürzen beschädigt werden. Warnungen zu solchen Mustern:

- `<SuppressTrimAnalysisWarnings>false</SuppressTrimAnalysisWarnings>`

    Aktivieren Sie Kürzungsanalysewarnungen.

Dies schließt Warnungen zur gesamten App ein, einschließlich Ihres eigenen Codes, Bibliothekscodes und Frameworkcodes.

## <a name="warning-versions"></a>Warnungsversionen

Bei der Kürzungsanalyse wird die [`AnalysisLevel`](../project-sdk/msbuild-props.md#analysislevel)-Eigenschaft berücksichtigt, die die Version der Analysewarnungen im gesamten SDK steuert. Es gibt eine andere Eigenschaft, die die Version von Kürzungsanalysewarnungen unabhängig voneinander steuert (ähnlich wie `WarningLevel` für den Compiler):

- `<ILLinkWarningLevel>5</ILLinkWarningLevel>`

    Es werden nur Warnungen der angegebenen Ebene oder niedriger ausgegeben. Dies kann `9999` sein, um alle Warnungsversionen einzubeziehen.

## <a name="suppressing-warnings"></a>Unterdrücken von Warnungen

Einzelne [Warnungscodes](https://github.com/mono/linker/blob/master/docs/error-codes.md#warning-codes) können mithilfe der üblichen MSBuild-Eigenschaften unterdrückt werden, die von der Toolkette einschließlich `NoWarn`, `WarningsAsErrors`, `WarningsNotAsErrors` und `TreatWarningsAsErrors` berücksichtigt werden. Es gibt eine zusätzliche Option, mit der das ILLink-Verhalten zum Warnen vor Fehlern unabhängig gesteuert wird:

- `<ILLinkTreatWarningsAsErrors>false</ILLinkTreatWarningsAsErrors>`

    Behandeln Sie ILLink-Warnungen nicht als Fehler. Dies kann hilfreich sein, um zu vermeiden, dass Kürzungsanalysewarnungen zu Fehlern werden, wenn Compilerwarnungen global als Fehler behandelt werden.

## <a name="removing-symbols"></a>Entfernen von Symbolen

Symbole werden normalerweise entfernt, um den gekürzten Assemblys zu entsprechen. Sie können auch alle Symbole entfernen:

- `<TrimmerRemoveSymbols>true</TrimmerRemoveSymbols>`

    Entfernen Sie Symbole aus der gekürzten Anwendung einschließlich eingebetteter und separater PDB-Dateien. Dies gilt sowohl für den Anwendungscode als auch für alle Abhängigkeiten mit Symbolen.

Das SDK ermöglicht außerdem die Deaktivierung der Debuggerunterstützung mithilfe der Eigenschaft `DebuggerSupport`. Wenn die Debuggerunterstützung deaktiviert ist, werden Symbole durch die Kürzung automatisch entfernt (`TrimmerRemoveSymbols` wird standardmäßig „true“).

## <a name="trimming-framework-library-features"></a>Kürzen von Frameworkbibliotheksfeatures

Mehrere Featurebereiche der Frameworkbibliotheken enthalten Linkeranweisungen, die es ermöglichen, den Code für deaktivierte Features zu entfernen.

- `<DebuggerSupport>false</DebuggerSupport>`

    Hiermit entfernen Sie Code, um das Debuggen verbessern zu können. Dadurch werden auch [Symbole entfernt](#removing-symbols).

- `<EnableUnsafeBinaryFormatterSerialization>false</EnableUnsafeBinaryFormatterSerialization>`

    Hiermit entfernen Sie die BinaryFormatter-Serialisierungsunterstützung. Weitere Informationen finden Sie unter [BinaryFormatter-Serialisierungsmethoden sind veraltet und in ASP.NET-Apps verboten](../compatibility/corefx.md#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps).

- `<EnableUnsafeUTF7Encoding>false</EnableUnsafeUTF7Encoding>`

    Hiermit wird unsicherer UTF-7-Codierungscode entfernt. Weitere Informationen finden Sie unter [UTF-7-Codepfade sind veraltet](../compatibility/corefx.md#utf-7-code-paths-are-obsolete).

- `<EventSourceSupport>false</EventSourceSupport>`

    Hiermit entfernen Sie Code oder Logik, der bzw. die mit EventSource verknüpft ist.

- `<HttpActivityPropagationSupport>false</HttpActivityPropagationSupport>`

    Hiermit entfernen Sie Code, der im Zusammenhang mit der Diagnoseunterstützung für System.Net.Http steht.

- `<InvariantGlobalization>true</InvariantGlobalization>`

    Hiermit entfernen Sie globalisierungsspezifischen Code und globalisierungsspezifische Daten. Weitere Informationen finden Sie unter [Invarianter Modus](../run-time-config/globalization.md#invariant-mode).

- `<UseSystemResourceKeys>true</UseSystemResourceKeys>`

    Entfernen Sie Ausnahmemeldungen für `System.*`-Assemblys. Wenn eine Ausnahme von einer `System.*`-Assembly ausgelöst wird, ist die Nachricht eine vereinfachte Ressourcen-ID anstelle der vollständigen Nachricht.

 Diese Eigenschaften bewirken, dass der zugehörige Code abgeschnitten wird. Außerdem werden über die [runtimeconfig](../run-time-config/index.md)-Datei Features deaktiviert. Weitere Informationen zu diesen Eigenschaften einschließlich der entsprechenden runtimeconfig-Optionen finden Sie unter [Featureschalter](https://github.com/dotnet/runtime/blob/master/docs/workflow/trimming/feature-switches.md). Einige SDKs verfügen möglicherweise über Standardwerte für diese Eigenschaften.
