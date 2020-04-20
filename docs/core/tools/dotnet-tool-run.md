---
title: Befehl „dotnet tool run“
description: Mit dem Befehl „dotnet tool run“ wird ein lokales Tool aufgerufen.
ms.date: 02/14/2020
ms.openlocfilehash: f79c239363e8b3abbd55c54dd1912443e6777fb7
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463325"
---
# <a name="dotnet-tool-run"></a>dotnet tool run

**Dieser Artikel gilt für:** ✔️ .NET Core 3.0 SDK und neuere Versionen

## <a name="name"></a>name

`dotnet tool run`: ruft ein lokales Tool auf.

## <a name="synopsis"></a>Übersicht

```dotnetcli
dotnet tool run <COMMAND NAME>

dotnet tool run -h|--help
```

## <a name="description"></a>Beschreibung

Der `dotnet tool run`-Befehl durchsucht Manifestdateien des Tools, die sich im Geltungsbereich des aktuellen Verzeichnisses befinden. Wenn ein Verweis auf das angegebene Tool gefunden wird, wird das Tool ausgeführt. Weitere Informationen finden Sie unter [Aufrufen eines lokalen Tools](global-tools.md#invoke-a-local-tool).

## <a name="arguments"></a>Argumente

- **`COMMAND_NAME`**

  Der Befehlsname des auszuführenden Tools.

## <a name="options"></a>Optionen

- **`-h|--help`**

  Druckt eine kurze Hilfe für den Befehl.

## <a name="example"></a>Beispiel

- **`dotnet tool run dotnetsay`**

  Führt das lokale Tool `dotnetsay` aus.

## <a name="see-also"></a>Siehe auch

- [.NET Core-Tools](global-tools.md)
- [Tutorial: Erstellen und Verwenden eines lokalen .NET Core-Tools mithilfe der .NET Core-CLI](local-tools-how-to-use.md)
