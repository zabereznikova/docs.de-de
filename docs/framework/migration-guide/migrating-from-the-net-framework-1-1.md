---
title: Migrieren von .NET Framework 1.1
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
ms.openlocfilehash: f74b75827770524299f9a25a5854503186139cb4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126297"
---
# <a name="migrating-from-the-net-framework-11"></a>Migrieren von .NET Framework 1.1

[!INCLUDE[win7](../../../includes/win7-md.md)] und neuere Versionen des Windows-Betriebssystems unterstützen .NET Framework 1.1 nicht. Folglich können Anwendungen, die auf .NET Framework 1.1 ausgerichtet sind, unter [!INCLUDE[win7](../../../includes/win7-md.md)] oder neueren Betriebssystemversionen nicht ohne Änderung ausgeführt werden. In diesem Thema werden die Schritte zum Ausführen einer Anwendung erläutert, die auf .NET Framework 1.1 unter [!INCLUDE[win7](../../../includes/win7-md.md)] und neueren Versionen des Windows-Betriebssystems ausgerichtet ist. Weitere Informationen zu .NET Framework 1.1 und [!INCLUDE[win8](../../../includes/win8-md.md)] finden Sie unter [Ausführen von auf .NET Framework 1.1 basierenden Apps unter Windows 8 und höher](../install/run-net-framework-1-1-apps.md).

## <a name="retargeting-or-recompiling"></a>Zuweisen einer neuen Zielversion oder Neukompilieren

Es gibt zwei Möglichkeiten, eine mit .NET Framework 1.1 kompilierte Anwendung unter [!INCLUDE[win7](../../../includes/win7-md.md)] oder neueren Versionen des Windows-Betriebssystems auszuführen:

- Sie können die Anwendung für die Ausführung unter .NET Framework 4 und späteren Versionen neu ausrichten. Für Neuausrichtung müssen Sie der Konfigurationsdatei der Anwendung, die das Ausführen unter .NET Framework 4 und späteren Versionen ermöglicht, ein [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md)-Element hinzufügen. Diese Konfigurationsdatei besitzt das folgende Format:

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0"/>
       </startup>
    </configuration>
    ```

- Sie können die Anwendung mit einem Compiler, der auf .NET Framework 4 oder eine spätere Version ausgerichtet ist, neu kompilieren. Wenn Sie ursprünglich Visual Studio 2003 zum Entwickeln und Kompilieren Ihrer Projektmappe verwendet haben, können Sie die Projektmappe in Visual Studio 2010 (und möglicherweise auch in späteren Versionen) öffnen. Die Projektmappe und die Projektdateien können dann über das Dialogfeld **Projektkompatibilität** aus den von Visual Studio 2003 verwendeten Formaten in das Format von Microsoft Build Engine (MSBuild) konvertiert werden.

Unabhängig davon, ob Sie eine Neukompilierung oder eine neue Zielversion für die Anwendung vorziehen, müssen Sie bestimmen, ob die Anwendung von Änderungen betroffen ist, die in höheren Versionen von .NET Framework eingeführt wurden. Diese Änderungen sind von zweierlei Art:

- Breaking Changes zwischen .NET Framework 1.1 und höheren Versionen von .NET Framework, die die Lauffähigkeit der Anwendung beeinträchtigen.

- Typen und Typmember, die zwischen .NET Framework 1.1 und höheren Versionen von .NET Framework als veraltet markiert wurden.

Überprüfen Sie beim Zuweisen einer neuen Zielversion und auch beim Neukompilieren Ihrer Anwendung sowohl die Breaking Changes als auch die veralteten Typen und Member für jede Version von .NET Framework, die nach .NET Framework 1.1 veröffentlicht wurde.

## <a name="breaking-changes"></a>Die Lauffähigkeit der Anwendung beeinträchtigende Änderungen

Bei einer Änderung, die die Lauffähigkeit der Anwendung beeinträchtigt, ist ggf. eine Problemumgehung sowohl für Anwendungen mit neuer Zielversion als auch für neu kompilierte Anwendungen verfügbar. In einigen Fällen können Sie dem [\<runtime>](../configure-apps/file-schema/startup/supportedruntime-element.md)-Element der Konfigurationsdatei der Anwendung ein untergeordnetes Element hinzufügen, um das vorherige Verhalten wiederherzustellen. Die folgende Konfigurationsdatei stellt z.B. die in .NET Framework 1.1 verwendete Zeichenfolgensortierung und das Vergleichsverhalten wieder her und kann bei neu zugewiesener Zielversion oder einer neu kompilierten Anwendung verwendet werden.

```xml
<configuration>
   <runtime>
      <CompatSortNLSVersion enabled="4096"/>
   </runtime>
</configuration>
```

In einigen Fällen müssen Sie jedoch möglicherweise den Quellcode ändern und die Anwendung neu kompilieren.

Überprüfen Sie die folgende Änderungsliste, um die Auswirkungen möglicher Änderungen zu bewerten, die die Lauffähigkeit der Anwendung beeinträchtigen:

- Unter [Breaking Changes in .NET Framework 2.0](https://go.microsoft.com/fwlink/?LinkId=125263) werden Änderungen in .NET Framework 2.0 SP1 erläutert, die Auswirkungen auf eine auf .NET Framework 1.1 ausgerichtet Anwendung haben können.

- Unter [Änderungen in .NET Framework 3.5 SP1](https://go.microsoft.com/fwlink/?LinkID=186989) werden Änderungen zwischen .NET Framework 3.5 und .NET Framework 3.5 SP1 dokumentiert.

- Unter[Migrationsprobleme in .NET Framework 4](net-framework-4-migration-issues.md) werden Änderungen zwischen .NET Framework 3.5 SP1 und .NET Framework 4 dokumentiert.

## <a name="obsolete-types-and-members"></a>Veraltete Typen und Member

Die Auswirkungen veralteter Typen und Member unterscheiden sich geringfügig bei Anwendungen mit neu zugewiesener Zielversion und neu kompilierten Anwendungen. Die Verwendung veralteter Typen und Member wirkt sich nicht auf eine Anwendung mit neuer Zielversion aus, sofern der veraltete Typ oder Member nicht physisch aus seiner Assembly entfernt wurde. Das Neukompilieren eine Anwendung, die veraltete Typen oder Member verwendet, erzeugt in der Regel eher eine Compilerwarnung als einen Compilerfehler. In einigen Fällen wird jedoch ein Compilerfehler verursacht, und Code, in dem der veraltete Typ oder Member verwendet wird, kann nicht erfolgreich kompiliert werden. Sie müssen dann den Quellcode neu schreiben, der den veralteten Typ oder Member aufruft, bevor Sie die Anwendung neu kompilieren. Weitere Informationen zu veralteten Typen und Membern finden Sie unter [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md).

Nähere Informationen zur Bewertung der Auswirkungen von Typen und Membern, die seit dem Release von .NET Framework 2.0 SP1 veraltet sind, finden Sie unter [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md). Überprüfen Sie die Listen der veralteten Typen und Member für .NET Framework 2.0 SP1, .NET Framework 3.5 und .NET Framework 4.
