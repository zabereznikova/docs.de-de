---
title: Befehl „dotnet tool run“
description: Mit dem Befehl „dotnet tool run“ wird ein lokales Tool aufgerufen.
ms.date: 02/14/2020
ms.openlocfilehash: 116ecb61748a0ca70ed385b279b11b939748f4a8
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634154"
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

- [.NET-Tools](global-tools.md)
- [Tutorial: Installieren und Verwenden eines lokalen .NET-Tools mithilfe der .NET-CLI](local-tools-how-to-use.md)
