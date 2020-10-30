---
ms.openlocfilehash: 959d8cb6d3e52916f6777054f3e9b327dc8edb4e
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434901"
---
### <a name="global-assembly-cache-apis-are-obsolete"></a>APIs für den globalen Assemblycache sind veraltet

.NET Core und .NET 5.0 sowie höhere Versionen verzichten auf das Konzept des globalen Assemblycaches (GAC), das in .NET Framework vorhanden war. Daher treten bei allen APIs für .NET Core und .NET 5 sowie höhere Versionen im Zusammenhang mit dem GAC Fehler auf, oder die APIs führen keinen Vorgang aus.

Einige GAC-bezogene APIs werden als veraltet markiert und generieren zur Kompilierzeit die Warnung `SYSLIB0005`, damit Entwickler zunehmend andere APIs verwenden. Diese APIs werden unter Umständen aus zukünftigen Versionen von .NET entfernt.

#### <a name="change-description"></a>Änderungsbeschreibung

Die folgenden APIs sind als veraltet markiert.

| API | Als veraltet markiert in... |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | 5.0 RC1 |

In .NET Framework 2.x bis 4.x gibt die Eigenschaft <xref:System.Reflection.Assembly.GlobalAssemblyCache> `true` zurück, wenn die abgefragte Assembly aus dem GAC geladen wurde. `false` wird zurückgegeben, wenn die Assembly aus einem anderen Speicherort auf dem Datenträger geladen wurde. In .NET Core 2.x bis 3.x gibt <xref:System.Reflection.Assembly.GlobalAssemblyCache> immer `false` zurück, was deutlich macht, dass der GAC in .NET Core nicht vorhanden ist.

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

In .NET 5.0 und höheren Versionen gibt die Eigenschaft <xref:System.Reflection.Assembly.GlobalAssemblyCache> auch weiterhin immer `false` zurück. Der Getter für die Eigenschaft ist jedoch ebenfalls als veraltet markiert, um Aufrufer darauf hinzuweisen, dass sie nicht mehr auf die Eigenschaft zugreifen sollen. Bibliotheken und Apps sollten die <xref:System.Reflection.Assembly.GlobalAssemblyCache>-API nicht beim Festlegen des Laufzeitverhaltens verwenden, da diese in .NET Core und .NET 5.0 sowie höheren Versionen immer `false` zurückgibt.

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

Dies ist eine Änderung, die nur die Kompilierzeit betrifft. Hinsichtlich der Laufzeit gibt es keine Änderung im Vergleich zu früheren Versionen von .NET Core.

#### <a name="reason-for-change"></a>Grund für die Änderung

Der globale Assemblycache (GAC) ist nicht als Konzept in .NET Core und .NET 5.0 und höheren Versionen vorhanden.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

#### <a name="recommended-action"></a>Empfohlene Aktion

- Wenn die Anwendung die <xref:System.Reflection.Assembly.GlobalAssemblyCache>-Eigenschaft abfragt, sollten Sie den Aufruf entfernen. Wenn Sie den Wert <xref:System.Reflection.Assembly.GlobalAssemblyCache> verwenden, um zur Laufzeit zwischen Flows zu wählen, bei denen sich die Assembly entweder im GAC oder nicht im GAC befindet, sollten Sie sich überlegen, ob der Flow auch für eine .NET Core- oder .NET 5.0-Anwendung (oder höher) geeignet ist.

- Wenn Sie die veralteten APIs weiterhin verwenden müssen, können Sie die Warnung `SYSLIB0005` im Code unterdrücken.

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  Sie können die Warnung auch in Ihrer Projektdatei unterdrücken, wodurch die Warnung für alle Quelldateien im Projekt deaktiviert wird.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  Durch das Unterdrücken von `SYSLIB0005` wird nur die Veraltungswarnung <xref:System.Reflection.Assembly.GlobalAssemblyCache> deaktiviert. Andere Warnungen werden nicht deaktiviert.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
