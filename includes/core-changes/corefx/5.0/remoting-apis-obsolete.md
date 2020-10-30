---
ms.openlocfilehash: 35041a035041fd4ad5402e1bc0dd137a74d4f949
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434967"
---
### <a name="remoting-apis-are-obsolete"></a>Remoting-APIs sind veraltet

Einige Remoting-bezogene APIs werden als veraltet gekennzeichnet und lösen zur Kompilierzeit die Warnung `SYSLIB0010` aus. Diese APIs werden unter Umständen aus zukünftigen Versionen von .NET entfernt.

#### <a name="change-description"></a>Änderungsbeschreibung

Die folgenden APIs sind als veraltet markiert.

| API | Als veraltet markiert in... |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | 5.0 RC1 |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | 5.0 RC1 |

In .NET Framework 2.x bis 4.x steuern die Methoden <xref:System.MarshalByRefObject.GetLifetimeService> und <xref:System.MarshalByRefObject.InitializeLifetimeService> die Lebensdauer von Instanzen, die an .NET-Remoting beteiligt sind. In .NET Core 2.x bis 3.x lösen diese Methoden zur Laufzeit immer eine Ausnahme des Typs <xref:System.PlatformNotSupportedException> aus.

In .NET 5.0 und höher sind die Methoden <xref:System.MarshalByRefObject.GetLifetimeService> und <xref:System.MarshalByRefObject.InitializeLifetimeService> durch eine Warnung als veraltet gekennzeichnet, lösen jedoch weiterhin zur Laufzeit eine Ausnahme des Typs <xref:System.PlatformNotSupportedException> aus.

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

Dies ist eine Änderung, die nur die Kompilierzeit betrifft. Hinsichtlich der Laufzeit gibt es keine Änderung im Vergleich zu früheren Versionen von .NET Core.

#### <a name="reason-for-change"></a>Grund für die Änderung

[.NET-Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) ist eine Legacytechnologie. Sie ermöglicht das Instanziieren eines Objekts in einem anderen Prozess (möglicherweise sogar auf einem anderen Computer) und das Interagieren mit diesem Objekt, als wäre es eine gewöhnliche In-Process-.NET-Objektinstanz. Die Infrastruktur für das .NET-Remoting ist nur in .NET Framework 2.x bis 4.x vorhanden. .NET Core sowie .NET 5.0 und höher bieten keine Unterstützung für .NET-Remoting, und die Remoting-APIs sind entweder nicht vorhanden oder lösen in diesen Runtimes immer Ausnahmen aus.

Damit Entwickler zunehmend andere APIs verwenden, werden ausgewählte Remoting-APIs als veraltet markiert. Diese APIs werden unter Umständen vollständig aus zukünftigen Versionen von .NET entfernt.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

#### <a name="recommended-action"></a>Empfohlene Aktion

- Sie sollten unter Umständen WCF- oder HTTP-basierte REST-Dienste verwenden, um mit Objekten in anderen Anwendungen oder auf anderen Computern zu kommunizieren. Weitere Informationen finden Sie unter [In .NET Core nicht verfügbare .NET Framework-Technologien](../../../../docs/core/porting/net-framework-tech-unavailable.md).

- Wenn Sie die veralteten APIs weiterhin verwenden müssen, können Sie die Warnung `SYSLIB0010` im Code unterdrücken.

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  Sie können die Warnung auch in Ihrer Projektdatei unterdrücken, wodurch die Warnung für alle Quelldateien im Projekt deaktiviert wird.

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  Durch das Unterdrücken von `SYSLIB0010` werden nur Veraltungswarnungen für die Remoting-APIs deaktiviert. Andere Warnungen werden nicht deaktiviert. Außerdem wird das hartcodierte Laufzeitverhalten nicht geändert, das darin besteht, <xref:System.PlatformNotSupportedException> immer auszulösen.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
