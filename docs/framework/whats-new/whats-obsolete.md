---
title: Veraltete Elemente in .NET Framework
description: Hier erfahren Sie, wie die .NET-Klassenbibliothek Member als veraltet kennzeichnet. Sie erhalten Informationen zum ObsoleteAttribute-Attribut und beispielsweise dazu, wie Sie veraltete Typen und Member verarbeiten.
ms.date: 04/02/2019
helpviewer_keywords:
- obsolete [.NET Framework]
- what's obsolete [.NET Framework]
- deprecated [.NET Framework]
ms.assetid: d356a43a-73df-4ae2-a457-b9628074c7cd
ms.openlocfilehash: 188d9184476e58fb679421467cd68e2ea8a8a101
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558867"
---
# <a name="whats-obsolete-in-the-net-framework-class-library"></a>Veraltete Elemente in der .NET Framework-Klassenbibliothek

.NET ändert sich im Laufe der Zeit. Jede neue Version erhält neue Typen und Typmember, die neue Funktionen bieten. Vorhandene Typen und deren Member werden im Laufe der Zeit ebenfalls geändert. Einige Typen verlieren z. B. an Bedeutung, da die von ihnen unterstützte Technologie durch eine neue Technologie ersetzt wird, und einige Methoden werden von neueren Methoden abgelöst, die den alten überlegener sind.

.NET Framework und die Common Language Runtime sollen Abwärtskompatibilität unterstützen (dadurch können Anwendungen, die mit einer bestimmten Version von .NET Framework entwickelt wurden, unter der nächsten Version von .NET Framework ausgeführt werden). Dadurch wird es schwierig, einfach einen Typ oder einen Typmember zu entfernen. Stattdessen gibt .NET an, dass ein Typ oder Typmember nicht mehr verwendet werden sollte, indem er als veraltet markiert wird. Ein veralteter Typ oder Member muss entsprechend markiert werden, damit Entwickler Bescheid wissen, dass er entfernt werden soll und die Zeit haben, auf das Entfernen des Typs zu reagieren. Allerdings wird vorhandener Code, in dem der Typ oder Member verwendet wird, weiterhin in der neuen Version von .NET ausgeführt.

> [!NOTE]
> Die Begriffe *veraltet* und *nicht mehr aktuell* haben die gleiche Bedeutung, wenn sie in Bezug auf die .NET-Typen und -Member angewendet werden.

## <a name="the-obsoleteattribute-attribute"></a>Das ObsoleteAttribute-Attribut

.NET Framework gibt an, dass ein Typ oder ein Typmember veraltet ist, indem er mit dem <xref:System.ObsoleteAttribute>-Attribut markiert wird. Das Anwenden des Attributs auf einen Typ oder Member gibt an, dass der Typ oder Member in einer künftigen Version von .NET Framework entfernt wird, ohne dass kompilierter Code in Mitleidenschaft gezogen wird, der diesen Member verwendet.

Neben der Angabe, dass ein Typ oder Typmember veraltet ist, wird mit <xref:System.ObsoleteAttribute> definiert, wie der Compiler Quellcode behandelt, der den Typ oder Member enthält. Der Compiler kann den Code kompilieren, aber eine Warnmeldung ausgeben, oder er kann die Verwendung des Typs oder Members als Fehler behandeln. Im ersten Fall kann der Code kompiliert werden, doch eine Warnmeldung zeigt an, dass der Typ oder der Member veraltet ist. Im zweiten Fall schlägt die Kompilierung fehl.

Auch wenn bei einer Kompilierung keine Warnmeldung angezeigt wird, sondern ein Fehler auftritt, wirkt sich <xref:System.ObsoleteAttribute> nicht auf das Laufzeitverhalten aus. Das heißt, dass Anwendungen, die den Typ oder den Member verwenden und die kompiliert wurden, immer ausgeführt werden. Nur der Versuch der erneuten Kompilierung einer Anwendung, die den Typ oder Member verwendet, schlägt fehl.

## <a name="how-to-handle-obsolete-types-and-members"></a>Behandeln von veralteten Typen und Membern

Wenn Sie vorhandenen Code aktualisieren und neu kompilieren, kann ohne weiteres ein veralteter Typ oder Member verwendet werden, durch den eine Compilerwarnung in der Anwendung erzeugt wird. Lesen Sie jedoch die Compilerwarnungsmeldung, um festzustellen, ob der Anwendungscode geändert werden sollte. Wenn in der Meldung nicht auf eine geeignete Alternative hingewiesen wird, führen Sie einen der folgenden Schritte aus:

- Ändern Sie, falls möglich, den Code durch Entfernen der Verwendung des Typs oder des Members.

     - oder -

- Lesen Sie die Dokumentation für diesen Technologiebereich, um zu bestimmen, wie darauf reagiert werden soll, dass die Komponente veraltet ist.

Sie können sich dazu entscheiden, keinen vorhandenen Code für eine höhere Version von .NET Framework neu zu kompilieren. Stattdessen können Sie die Version von .NET Framework angeben, für die der vorhandene kompilierte Code ausgeführt wird. Ein Beispiel: Angenommen, Sie besitzen eine für .NET Framework 3.5 kompilierte Anwendung mit dem Namen „app1.exe“ und möchten, dass diese Anwendung für .NET Framework 4.5 ausgeführt wird. Gehen Sie dazu folgendermaßen vor:

1. Erstellen Sie eine Konfigurationsdatei für die zentrale ausführbare Datei, und nennen Sie diese *appName*.exe.config, wobei *appName* der Name der ausführbaren Datei der Anwendung ist. Für die Anwendung mit dem Namen *app1.exe* in diesem Beispiel würden Sie eine Konfigurationsdatei mit dem Namen *app1.exe.config* erstellen.

2. Fügen Sie der Konfigurationsdatei Folgendes hinzu:

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0" />
       </startup>
    </configuration>
    ```

Um eine bestimmte Version von .NET Framework als Ziel zu verwenden, weisen Sie dem `version`-Attribut einen der folgenden Zeichenfolgenwerte zu:

|.NET Framework-Version|`version`-Zeichenfolge|
|-|-|
|4.8|v4.0|
|4.7 (einschließlich 4.7.1 und 4.7.2)|v4.0|
|4.6 (einschließlich 4.6.1 und 4.6.2)|v4.0|
|4.5 (inklusive 4.5.1 und 4.5.2)|v4.0|
|4|v4.0|
|3.5|v2.0.50727|
|2.0|v2.0.50727|
|1.1|v1.1.4322|
|1.0|v1.0.3705|

## <a name="obsolete-apis-for-net-framework-45-and-later-versions"></a>Veraltete APIs für .NET Framework 4.5 und höhere Versionen

- [Veraltete Typen](obsolete-types.md)
- [Veraltete Member](obsolete-members.md)

## <a name="obsolete-apis-for-previous-versions"></a>Veraltete APIs für frühere Versionen

- [Veraltete Typen in .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee461503(v=vs.100))
- [Veraltete Member in .NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ee471421(v=vs.100))
- [Liste veralteter Elemente in .NET Framework 3.5](https://docs.microsoft.com/previous-versions/cc835481(v=msdn.10))
- [Liste veralteter Elemente in .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa497286(v=msdn.10))

## <a name="see-also"></a>Siehe auch

- [\<supportedRuntime>-Element](../configure-apps/file-schema/startup/supportedruntime-element.md)
