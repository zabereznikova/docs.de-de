---
title: -subsystemversion
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: a977bc4cff822de551bf82d0f31707e9b2b6ea41
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348539"
---
# <a name="-subsystemversion-visual-basic"></a>-SubSystemVersion (Visual Basic)

Gibt die Mindestversion des Subsystems an, das die erzeugte ausführbare Datei ausführen kann. Dabei bestimmt sie die Version von Windows, auf der die ausführbare Datei ausgeführt werden kann. In den meisten Fällen stellt diese Option sicher, dass die ausführbare Datei bestimmte Sicherheitsfunktionen nutzt, die nicht in älteren Versionen von Windows verfügbar sind.

> [!NOTE]
> Verwenden Sie zum Angeben des Subsystems die Compileroption [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).

## <a name="syntax"></a>Syntax

```vb
-subsystemversion:major.minor
```

## <a name="parameters"></a>Parameter

`major.minor`

Die mindestens erforderliche Version des Subsystems wird in einer Punktschreibweise für Haupt- und Nebenversionen ausgedrückt. Beispielsweise können Sie angeben, dass eine Anwendung nicht unter einem Betriebssystem, das älter als Windows 7 ist, ausgeführt werden kann,wenn Sie den Werte dieser Option auf 6.01 festlegen, wie es in der Tabelle in diesem Thema zu einem späteren Zeitpunkt beschrieben wird. Sie müssen die Werte für `major` und `minor` als ganze Zahl angeben.

Führende Nullen in der Version `minor` ändern die Version nicht, jedoch nachfolgende Nullen. 6\.1 und 6.01 verweisen z.B. auf die gleiche Version, aber 6.10 verweist auf eine andere Version. Es wird empfohlen, die Nebenversion in Form von zwei Ziffern auszudrücken, um Verwechslungen zu vermeiden.

## <a name="remarks"></a>Hinweise

Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.

|Windows-Version|Subsystemversion|
|---------------------|-----------------------|
|Windows 2000|5.00|
|Windows XP|5.01|
|Windows Server 2003|5.02|
|Windows Vista|6.00|
|Windows 7|6,01|
|Windows Server 2008|6,01|
|[!INCLUDE[win8](~/includes/win8-md.md)]|6.02|

## <a name="default-values"></a>Standardwerte

Der Standardwert der Compileroption **-subsystemversion** hängt von den Bedingungen in der folgenden Liste ab:

- Der Standardwert ist 6,02, wenn jede Compileroption in der folgenden Liste festgelegt ist:

  - [/target:appcontainerexe](../../../visual-basic/reference/command-line-compiler/target.md)

  - [/target:winmdobj](../../../visual-basic/reference/command-line-compiler/target.md)

  - [-platform:arm](../../../visual-basic/reference/command-line-compiler/platform.md)

- Wenn Sie MSBuild verwenden, .NET Framework 4.5 als Ziel festlegen und keine der Compileroptionen verwenden, die weiter oben in der Liste angegeben sind, ist der Standardwert 6.00.

- Der Standardwert ist 4,00, wenn keine der vorherigen Bedingungen TRUE ist.

## <a name="setting-this-option"></a>Festlegen dieser Option

Um die **-SubSystemVersion-** Compileroption in Visual Studio festzulegen, müssen Sie die VBPROJ-Datei öffnen und einen Wert für die `SubsystemVersion`-Eigenschaft in der MSBuild-XML-Datei angeben. Diese Option kann nicht in der Visual Studio-IDE festgelegt werden. Weitere Informationen finden Sie unter „Standardwerte“ weiter oben in diesem Thema oder unter [Häufige MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)

- [MSBuild-Eigenschaften](/visualstudio/msbuild/msbuild-properties)
