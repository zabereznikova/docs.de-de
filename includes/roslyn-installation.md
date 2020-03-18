---
ms.openlocfilehash: 2872c5909b382e01fdd231019a12970caa3b77d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "72526748"
---
## <a name="installation-instructions---visual-studio-installer"></a>Installationsanweisungen: Visual Studio-Installer

Es gibt zwei verschiedene Möglichkeiten, das **.NET Compiler Platform SDK** im **Visual Studio-Installer** zu finden:

### <a name="install-using-the-visual-studio-installer---workloads-view"></a>Installation mithilfe des Visual Studio-Installers: Workloads im Überblick

Das .NET Compiler Platform SDK wird nicht automatisch als Teil der Workload „Visual Studio-Extensionentwicklung“ ausgewählt. Sie müssen sie als optionale Komponente auswählen.

1. Führen Sie den **Visual Studio-Installer** aus.
1. Klicken Sie auf **Ändern**.
1. Aktivieren Sie die Workload **Visual Studio-Extensionentwicklung**.
1. Öffnen Sie den Knoten **Visual Studio-Extensionentwicklung** in der Zusammenfassungsstruktur.
1. Aktivieren Sie das Kontrollkästchen für das **.NET Compiler Platform SDK**. Sie finden es an letzter Stelle unter den optionalen Komponenten.

Optional können Sie einstellen, dass der **DGML-Editor** Diagramme in der Schnellansicht anzeigt:

1. Öffnen Sie den Knoten **Einzelne Komponenten** in der Zusammenfassungsstruktur.
1. Aktivieren Sie das Kontrollkästchen für den **DGML-Editor**.

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a>Installation mithilfe des Visual Studio-Installers: Registerkarte „Einzelne Komponenten“

1. Führen Sie den **Visual Studio-Installer** aus.
1. Klicken Sie auf **Ändern**.
1. Klicken Sie auf die Registerkarte **Einzelne Komponenten**.
1. Aktivieren Sie das Kontrollkästchen für das **.NET Compiler Platform SDK**. Sie finden es an oberster Stelle im Abschnitt **Compiler, Buildtools und Laufzeiten**.

Optional können Sie einstellen, dass der **DGML-Editor** Diagramme in der Schnellansicht anzeigt:

1. Aktivieren Sie das Kontrollkästchen für den **DGML-Editor**. Sie finden es im Abschnitt **Codetools**.
