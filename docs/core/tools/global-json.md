---
title: 'global.json: Übersicht'
description: In diesem Artikel erfahren Sie, wie Sie mit der global.json-Datei die .NET Core SDK-Version beim Ausführen eines .NET Core-CLI-Befehls festgelegen.
ms.date: 12/03/2018
ms.custom: updateeachrelease
ms.openlocfilehash: 4da703266e98b209cdd031f4ea856b4d7c83930c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714173"
---
# <a name="globaljson-overview"></a>global.json: Übersicht

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

Mit der *global.json*-Datei können Sie definieren, welche .NET Core SDK-Version verwendet wird, wenn Sie .NET Core-CLI-Befehle ausführen. Die Auswahl der .NET Core SDK ist unabhängig von der Angabe der Laufzeit Ihrer Projektziele. Die .NET Core SDK-Version gibt an, welche Versionen der .NET Core-CLI-Tools verwendet werden. Wenn Sie die neueste Version der Tools verwenden möchten, wird in der Regel keine *global.json*-Datei benötigt.

Weitere Informationen zum Angeben der Laufzeit finden Sie unter [Zielframeworks](../../standard/frameworks.md).

.NET Core SDK sucht im aktuellen Arbeitsverzeichnis (das nicht dem Projektverzeichnis entsprechen muss) oder in einem übergeordneten Verzeichnis nach einer *global.json*-Datei.

## <a name="globaljson-schema"></a>global.json-Schema

### <a name="sdk"></a>SDK

Typ: Object

Gibt Informationen zum auszuwählenden .NET Core SDK an.

#### <a name="version"></a>Version

Typ: Zeichenfolge

Die Version des zu verwendenden .NET Core SDK.

Beachten Sie, dass dieses Feld:

- Keine Platzhalter unterstützt, d. h. die vollständige Versionsnummer muss angegeben werden
- Keine Versionsbereiche unterstützt

Das folgende Beispiel zeigt den Inhalt einer *global.json*-Datei an.

```json
{
  "sdk": {
    "version": "2.2.100"
  }
}
```

## <a name="globaljson-and-the-net-core-cli"></a>global.json und die .NET Core-CLI

Es ist nützlich zu wissen, welche Versionen verfügbar sind, um in der *global.json*-Datei eine Version festzulegen. Eine vollständige Liste der unterstützten und verfügbaren SDKs finden Sie auf der Seite [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core). Ab .NET Core 2.1 SDK können Sie den folgenden Befehl ausführen, um zu überprüfen, welche SDK-Versionen bereits auf Ihrem Computer installiert sind:

```dotnetcli
dotnet --list-sdks
```

Weitere .NET Core SDK-Versionen, die Sie auf Ihrem Computer installieren können, finden Sie unter [.NET Core herunterladen](https://dotnet.microsoft.com/download/dotnet-core).

Sie können im aktuellen Verzeichnis eine neue *global.json*-Datei erstellen, indem Sie den Befehl [dotnet new](dotnet-new.md) ausführen, wie im folgenden Beispiel:

```dotnetcli
dotnet new globaljson --sdk-version 2.2.100
```

## <a name="matching-rules"></a>Abgleichsregeln

> [!NOTE]
> Die Abgleichsregeln werden vom App-Host bestimmt, der der .NET Core-Laufzeit unterliegt.
> Wenn Sie mehrere Laufzeiten nebeneinander installiert haben, wird die neueste Version des Hosts verwendet.

Ab .NET Core 2.0 legen die folgenden Regeln fest, welche SDK-Version verwendet wird:

- Wenn keine *global.json*-Datei gefunden wird oder *global.json* keine SDK-Version angibt, wird die neueste installierte SDK-Version verwendet. Die neueste SDK-Version kann ein Release oder eine Vorabversion sein, es gilt die höchste Versionsnummer.
- Wenn *global.json* eine SDK-Version angibt:
  - Wenn die angegebene SDK-Version auf dem Computer gefunden wird, wird genaue diese Version verwendet.
  - Wenn die angegebene SDK-Version auf dem Computer nicht gefunden wird, wird die neueste installierte SDK-**Patchversion** der Version verwendet. Die neueste installierte SDK-**Patchversion** kann ein Release oder eine Vorabversion sein, es gilt die höchste Versionsnummer. In .NET Core 2.1 und höher werden die **Patchversionen**, die niedriger als die angegebene **Patchversion** sind, bei der SDK-Auswahl ignoriert.
  - Wenn die angegebene SDK-Version und eine entsprechende SDK-**Patchversion** nicht gefunden werden, wird ein Fehler ausgelöst.

Die SDK-Version hat zurzeit folgende Bestandteile:

`[.NET Core major version].[.NET Core minor version].[xyz][-optional preview name]`

Die **Funktionsfreigabe** von .NET Core SDK wird für SDK-Versionen ab 2.1.100 von der ersten Ziffer (`x`) im letzten Teil der Nummer (`xyz`) dargestellt. Generell hat .NET Core SDK einen schnelleren Releasezyklus als .NET Core.

Die **Patchversion** wird für SDK-Versionen ab 2.1.100 von den letzten beiden Ziffern (`yz`) im letzten Teil der Nummer (`xyz`) definiert. Wenn Sie beispielsweise `2.1.300` als SDK-Version angeben, werden für die SDK-Auswahl Versionen bis `2.1.399` berücksichtigt, allerdings wird `2.1.400` nicht als Patchversion von `2.1.300` betrachtet.

.NET Core SDK-Versionen `2.1.100` bis `2.1.201` wurden beim Übergang zwischen Versionsnummerschemen freigegeben und halten die `xyz`-Notation nicht ordnungsgemäß ein. Falls Sie diese Versionen in der *global.json*-Datei angeben, wird dringend empfohlen sicherzustellen, dass sich die angegebenen Versionen auf den Zielcomputern befinden.

Mit .NET Core SDK 1.x wurde die neueste installierte SDK-Version verwendet, wenn Sie eine Version angegeben haben und keine genaue Übereinstimmung gefunden wurde. Die neueste SDK-Version kann ein Release oder eine Vorabversion sein, es gilt die höchste Versionsnummer.

## <a name="troubleshooting-build-warnings"></a>Problembehandlung bei Buildwarnungen

> [!WARNING]
> Sie verwenden eine Vorschauversion von .NET Core SDK. Sie können die SDK-Version über eine global.json-Datei im aktuellen Projekt definieren. Weitere Informationen finden Sie unter <https://go.microsoft.com/fwlink/?linkid=869452>.

Diese Warnung weist darauf hin, dass das Projekt mit einer .NET Core SDK-Vorschauversion kompiliert wird, wie im Abschnitt [Abgleichsregeln](#matching-rules) beschrieben. .NET Core SDK-Versionen haben einen Verlauf und weisen eine hohe Qualität auf. Wenn Sie jedoch keine Vorschauversion verwenden möchten, fügen Sie Ihrer Projekthierarchiestruktur eine *global.json*-Datei hinzu, um die zu verwendende SDK-Version anzugeben, und bestätigen Sie mithilfe von `dotnet --list-sdks`, dass die Version auf Ihrem Computer installiert ist. Wenn eine neue Version verfügbar ist, entfernen Sie entweder die *global.json*-Datei oder aktualisieren Sie sie, um die neuere Version zu verwenden.

> [!WARNING]
> Das Startprojekt „{startupProject}“ gibt Version „{targetFrameworkVersion}“ von Framework „.NETCoreApp“ als Ziel an. Diese Version der Entity Framework Core .NET-Befehlszeilentools unterstützt nur Version 2.0 oder höher. Weitere Informationen zur Verwendung älterer Toolversionen finden Sie unter <https://go.microsoft.com/fwlink/?linkid=871254>.

Ab .NET Core 2.1 SDK (Version 2.1.300) ist der Befehl `dotnet ef` im SDK enthalten. Diese Warnung weist darauf hin, dass das Projekt EF Core 1.0 oder 1.1 als Ziel angibt, das nicht mit .NET Core 2.1 SDK oder höher kompatibel ist. Um Ihr Projekt zu kompilieren, installieren Sie das .NET Core 2.0 SDK (Version 2.1.201) und früher auf Ihrem Computer, und legen Sie mithilfe der Datei *global.json* die gewünschte SDK-Version fest. Weitere Informationen zu dem Befehl `dotnet ef` finden Sie unter [EF Core .NET-Befehlszeilentools](/ef/core/miscellaneous/cli/dotnet).

## <a name="see-also"></a>Siehe auch

- [Wie Projekt-SDKs gelöst werden](/visualstudio/msbuild/how-to-use-project-sdk#how-project-sdks-are-resolved)
