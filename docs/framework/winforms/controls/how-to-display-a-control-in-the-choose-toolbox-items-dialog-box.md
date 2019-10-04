---
title: 'Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“'
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 86ec8f9ae76f010ebbc3be393d8d257ba5cfc6b6
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834617"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“

Wenn Sie Steuerelemente entwickeln und verteilen, möchten Sie möglicherweise, dass diese Steuerelemente im Dialogfeld **Toolbox Elemente auswählen** von Visual Studio angezeigt werden, das angezeigt wird, wenn Sie mit der rechten Maustaste auf die **Toolbox** klicken und **Elemente auswählen**auswählen. Sie können das Steuerelement in diesem Dialogfeld mithilfe der AssemblyFoldersEx-Registrierungs Prozedur anzeigen lassen.

So zeigen Sie das Steuerelement im Dialogfeld Toolbox Elemente auswählen an:

- Installieren Sie die steuerungsassembly im globalen Assemblycache. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../app-domains/install-assembly-into-gac.md).

  - oder -

- Registrieren Sie das Steuerelement und die zugehörigen Entwurfszeit-Assemblys mithilfe der AssemblyFoldersEx-Registrierungs Prozedur. AssemblyFoldersEx ist ein Registrierungs Speicherort, an dem Drittanbieter Pfade für jede Version des Frameworks speichern, das Sie unterstützen. Die Entwurfszeit Auflösung kann in diesem Registrierungs Speicherort nach Verweisassemblys suchen. Das Registrierungs Skript kann die Steuerelemente angeben, die in der Toolbox angezeigt werden sollen.

## <a name="see-also"></a>Siehe auch

- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
- [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../app-domains/install-assembly-into-gac.md)
- [Exemplarische Vorgehensweise: Automatisches Auffüllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
