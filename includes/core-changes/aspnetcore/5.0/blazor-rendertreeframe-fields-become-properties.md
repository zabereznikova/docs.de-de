---
ms.openlocfilehash: edff55d540f08e8a9fd4d0687aaf6bd963ee3a84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539528"
---
### <a name="blazor-rendertreeframe-readonly-public-fields-have-become-properties"></a>Blazor: Schreibgeschützte öffentliche RenderTreeFrame-Felder sind jetzt Eigenschaften

In ASP.NET Core 3.0 und 3.1 machte die <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame>-Struktur verschiedene `readonly public`-Felder verfügbar, u. a. <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType> und <xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.Sequence>. Ab ASP.NET Core 5.0 RC1 wurden alle `readonly public`-Felder in `readonly public`-Eigenschaften geändert.

Diese Änderung wirkt sich aus folgenden Gründen nicht auf viele Entwickler aus:

* Jede Anwendung oder Bibliothek, die einfach `.razor`-Dateien (oder sogar manuelle <xref:Microsoft.AspNetCore.Components.Rendering.RenderTreeBuilder>-Aufrufe) verwendet, um ihre Komponenten zu definieren, würde nicht direkt auf diesen Typ verweisen.
* Der Typ `RenderTreeFrame` selbst wird als Implementierungsdetail betrachtet, das nicht für eine Verwendung außerhalb des Frameworks vorgesehen ist. Ab ASP.NET Core 3.0 steht ein Analysetool zur Verfügung, das Compilerwarnungen ausgibt, wenn der Typ direkt verwendet wird.
* Selbst wenn Sie direkt auf `RenderTreeFrame` verweisen, ist diese Änderung ein binärer Breaking Change, aber kein Breaking Change im Quellcode. Das heißt, dass der vorhandene Quellcode kompiliert wird und sich verhält ordnungsgemäß. Sie werden nur dann auf ein Problem stoßen, wenn Sie mit einem .NET Core 3.x-Framework kompilieren und diese Binärdateien dann mit dem .NET 5.0 RC1-Framework und höher ausführen.

Weitere Informationen finden Sie unter GitHub-Issue [dotnet/aspnetcore#25727](https://github.com/dotnet/aspnetcore/issues/25727).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC1

#### <a name="old-behavior"></a>Altes Verhalten

Öffentliche Member in `RenderTreeFrame` werden als Felder definiert. Beispiel: `renderTreeFrame.Sequence` und `renderTreeFrame.ElementName`.

#### <a name="new-behavior"></a>Neues Verhalten

Öffentliche Member in `RenderTreeFrame` werden als Eigenschaften mit denselben Namen wie zuvor definiert. Beispiel: `renderTreeFrame.Sequence` und `renderTreeFrame.ElementName`.

Wenn älterer vorkompilierter Code seit dieser Änderung nicht neu kompiliert wurde, kann er eine Ausnahme ähnlich dieser auslösen: *MissingFieldException: Feld nicht gefunden: Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame.FrameType*.

#### <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung war notwendig, um erhebliche Leistungsverbesserungen beim Rendering von Blazor-Komponenten in ASP.NET Core 5.0 zu implementieren. Die gleichen Sicherheits- und Kapselungsebenen bleiben erhalten.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Die meisten Blazor-Entwickler sind von dieser Änderung nicht betroffen. Die Änderung betrifft eher Ersteller von Bibliotheken und Paketen, aber nur in seltenen Fällen. Das gibt insbesondere, wenn Sie Folgendes entwickeln:

* Eine App und mit ASP.NET Core 3.x arbeiten oder ein Upgrade auf mindestens 5.0 RC1 vornehmen. Dann brauchen Sie Ihren eigenen Code nicht zu ändern. Wenn Sie jedoch von einer Bibliothek abhängig sind, für die ein Upgrade erfolgt ist, um diese Änderung zu berücksichtigen, müssen Sie auf eine neuere Version dieser Bibliothek aktualisieren.
* Eine Bibliothek und nur ASP.NET Core 5.0 RC1 oder höher unterstützen möchten. Dann ist keine Aktion erforderlich. Stellen Sie einfach sicher, dass Ihre Projektdatei den `<TargetFramework>`-Wert `net5.0` oder eine spätere Version deklariert.
* Eine Bibliothek und Sie sowohl ASP.NET Core 3.x *und* 5.0 unterstützen möchten. Dann müssen Sie bestimmen, ob Ihr Code `RenderTreeFrame`-Member liest. Beispielsweise beim Auswerten von `someRenderTreeFrame.FrameType`.
  * Die meisten Bibliotheken lesen keine `RenderTreeFrame`-Member, einschließlich Bibliotheken mit `.razor`-Komponenten. In diesem Fall ist keine Aktion erforderlich.
  * Wenn Ihre Bibliothek dies jedoch tut, müssen Sie mehrere Ziele abdecken, um sowohl `netstandard2.1` als auch `net5.0` zu unterstützen. Wenden Sie die folgenden Änderungen in Ihrer Projektdatei an:
    * Ersetzen Sie das vorhandene `<TargetFramework>`-Element durch `<TargetFrameworks>netstandard2.0;net5.0</TargetFrameworks>`.
    * Verwenden Sie einen bedingten Verweis auf das `Microsoft.AspNetCore.Components`-Paket, um beide Versionen zu berücksichtigen, die Sie unterstützen möchten. Zum Beispiel:

        ```xml
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="3.0.0" Condition="'$(TargetFramework)' == 'netstandard2.0'" />
        <PackageReference Include="Microsoft.AspNetCore.Components" Version="5.0.0-rc.1.*" Condition="'$(TargetFramework)' != 'netstandard2.0'" />
        ```

Weitere Erläuterungen finden sich in diesem [-Diff, das zeigt, wie @jsakamoto bereits die `Toolbelt.Blazor.HeadElement` Bibliothek](https://github.com/jsakamoto/Toolbelt.Blazor.HeadElement/commit/090df430ba725f9420d412753db8104e8c32bf51) aktualisiert hat.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.Components.RenderTree.RenderTreeFrame`

-->
