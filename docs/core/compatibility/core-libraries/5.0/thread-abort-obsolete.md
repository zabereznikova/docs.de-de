---
title: 'Breaking Change: Thread.Abort ist veraltet'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die Thread.Abort-APIs als veraltet gelten.
ms.date: 11/01/2020
ms.openlocfilehash: 6d7dfce8fda393bfd88c9b4cf0c59d53942cee25
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759220"
---
# <a name="threadabort-is-obsolete"></a>Thread.Abort ist veraltet

Die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-APIs sind veraltet. Bei Projekten für .NET 5.0 und höher wird bei Aufruf dieser Methoden zur Kompilierzeit die Warnung `SYSLIB0006` angezeigt.

## <a name="change-description"></a>Änderungsbeschreibung

Zuvor wurden bei Aufrufen von <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> keine Warnungen zur Kompilierzeit erzeugt. Die Methode löste jedoch zur Laufzeit die Ausnahme <xref:System.PlatformNotSupportedException> aus.

Ab .NET 5.0 ist <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> mit einer Warnung als veraltet gekennzeichnet. Beim Aufrufen dieser Methode wird die Compilerwarnung `SYSLIB0006` erzeugt. Die Implementierung der Methode bleibt unverändert, und die Ausnahme <xref:System.PlatformNotSupportedException> wird weiterhin ausgelöst.

## <a name="reason-for-change"></a>Grund für die Änderung

Da <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> immer für alle .NET-Implementierungen außer das .NET Framework die Ausnahme <xref:System.PlatformNotSupportedException> auslöst, wurde der Methode <xref:System.ObsoleteAttribute> hinzugefügt, um die Aufmerksamkeit auf die Stellen zu lenken, an denen diese Methode aufgerufen wird.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

- Verwenden Sie <xref:System.Threading.CancellationToken>, um die Verarbeitung einer Arbeitseinheit abzubrechen, statt <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> aufzurufen. Im folgenden Beispiel wird die Verwendung von <xref:System.Threading.CancellationToken> veranschaulicht.

  ```csharp
  void ProcessPendingWorkItemsNew(CancellationToken cancellationToken)
  {
      if (QueryIsMoreWorkPending())
      {
          // If the CancellationToken is marked as "needs to cancel",
          // this will throw the appropriate exception.
          cancellationToken.ThrowIfCancellationRequested();

          WorkItem work = DequeueWorkItem();
          ProcessWorkItem(work);
      }
  }
  ```

  Weitere Informationen finden Sie unter [Abbruch in verwalteten Threads](../../../../standard/threading/cancellation-in-managed-threads.md).

- Unterdrücken Sie den Warnungscode `SYSLIB0006`, um die Warnung zur Kompilierzeit zu unterdrücken. Dieser Warnungscode ist spezifisch für <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Bei seiner Unterdrückung werden folglich in Ihrem Code keine anderen Warnungen aufgrund von veralteten Elementen unterdrückt. Es wird jedoch empfohlen, die Aufrufe von <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> zu entfernen statt die Warnung zu unterdrücken.

  ```csharp
  void MyMethod()
  {
  #pragma warning disable SYSLIB0006
      Thread.CurrentThread.Abort();
  #pragma warning restore SYSLIB0006
  }
  ```

  Sie können die Warnung auch in der Projektdatei unterdrücken.

  ```xml
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
    <!-- Disable "Thread.Abort is obsolete" warnings for entire project. -->
    <NoWarn>$(NoWarn);SYSLIB0006</NoWarn>
  </PropertyGroup>
  ```

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Threading.Thread.Abort%2A?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `Overload:System.Threading.Thread.Abort`

-->
