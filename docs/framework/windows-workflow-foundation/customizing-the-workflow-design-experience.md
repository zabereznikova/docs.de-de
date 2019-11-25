---
title: Anpassen des Workflowentwurfsvorgangs
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 41be55391ae9481f6c2e4feb76443f7fb676b69d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141922"
---
# <a name="customizing-the-workflow-design-experience"></a>Anpassen des Workflowentwurfsvorgangs

Die Szenarien zum Entwerfen von benutzerdefinierten Aktivitäten und zum erneuten Hosting der [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] wurden in .NET Framework 4 erheblich vereinfacht. Die Entwicklung und Bereitstellung sind jetzt einfacher sowie flexibler. Die wesentliche Infrastrukturänderung besteht darin, dass das neue Programmiermodell des Aktivitäts Designers auf Windows Presentation Foundation (WPF) aufbaut. Dies ermöglicht Ihnen, Aktivitätsdesigner deklarativ zu definieren und den [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in anderen Anwendungen vergleichsweise einfach erneut zu hosten. Beim erneuten Hosten kann ein benutzerdefinierter Ausdrucks-Editor entwickelt werden, um IntelliSense oder eine vereinfachte Ausdrucksdomäne zu unterstützen. Die Integration mit Windows Communication Foundation (WCF) wurde mit der Verwendung von Workflow Diensten nahtlos. Benutzerdefinierte Aktivitätsdesigner und die Modellelementstruktur können verwendet werden, um die Entwurfszeiterfahrung in neu gehosteten Workflowdesignern zu verbessern.

## <a name="in-this-section"></a>In diesem Abschnitt

 [Verwenden benutzerdefinierter Aktivitätsdesigner und Vorlagen](using-custom-activity-designers-and-templates.md)

 Beschreibt die Erstellung eines neuen benutzerdefinierten Aktivitätsdesigners und von Vorlagen.

 [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)

 Hier wird beschrieben, wie Sie die [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] außerhalb von Visual Studio neu hosten und Validierungs Fehler anzeigen.

 [Verwenden eines benutzerdefinierten Ausdrucks-Editors](using-a-custom-expression-editor.md)

 Beschreibt, wie ein benutzerdefinierter Ausdrucks-Editor für die Verwendung mit Workflow-Designern implementiert wird, die außerhalb von Visual Studio 2010 neu gehostet werden.

## <a name="reference"></a>Referenz

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Siehe auch

- [Erweitern der Windows Workflow Foundation](extend.md)
- [Designer](./samples/designer.md)
- [Benutzerdefinierte Aktivitätsdesigner](./samples/custom-activity-designers.md)
- [Erneutes Hosten von Designern](./samples/designer-rehosting.md)
