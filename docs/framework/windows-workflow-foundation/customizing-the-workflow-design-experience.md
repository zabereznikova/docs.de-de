---
title: Anpassen des Workflowentwurfsvorgangs
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 27be398d874747b65ae051224070d3f40f1fbbb0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715139"
---
# <a name="customizing-the-workflow-design-experience"></a>Anpassen des Workflowentwurfsvorgangs

Die Szenarien zum Entwerfen von benutzerdefinierten Aktivitäten und zum erneuten Hosting der Windows-Workflow-Designer wurden in .NET Framework 4 erheblich vereinfacht. Die Entwicklung und Bereitstellung sind jetzt einfacher sowie flexibler. Die wesentliche Infrastrukturänderung besteht darin, dass das neue Programmiermodell des Aktivitäts Designers auf Windows Presentation Foundation (WPF) aufbaut. Dadurch haben Sie die Möglichkeit, Aktivitäts Designer deklarativ zu definieren und die Workflow-Designer in anderen Anwendungen mit Vergleichs einfachem Host zu hosten. Beim erneuten Hosten kann ein benutzerdefinierter Ausdrucks-Editor entwickelt werden, um IntelliSense oder eine vereinfachte Ausdrucksdomäne zu unterstützen. Die Integration mit Windows Communication Foundation (WCF) wurde mit der Verwendung von Workflow Diensten nahtlos. Benutzerdefinierte Aktivitätsdesigner und die Modellelementstruktur können verwendet werden, um die Entwurfszeiterfahrung in neu gehosteten Workflowdesignern zu verbessern.

## <a name="in-this-section"></a>In diesem Abschnitt

 [Verwenden benutzerdefinierter Aktivitätsdesigner und Vorlagen](using-custom-activity-designers-and-templates.md)

 Beschreibt die Erstellung eines neuen benutzerdefinierten Aktivitätsdesigners und von Vorlagen.

 [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)

 Hier wird beschrieben, wie Sie die Windows Workflow-Designer außerhalb von Visual Studio neu hosten und Validierungs Fehler anzeigen.

 [Verwenden eines benutzerdefinierten Ausdrucks-Editors](using-a-custom-expression-editor.md)

 Beschreibt, wie ein benutzerdefinierter Ausdrucks-Editor für die Verwendung mit Workflow-Designern implementiert wird, die außerhalb von Visual Studio 2010 neu gehostet werden.

## <a name="reference"></a>Referenz

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Siehe auch

- [Erweitern der Windows Workflow Foundation](extend.md)
- [Designer](./samples/designer.md)
- [Benutzerdefinierte Aktivitätsdesigner](./samples/custom-activity-designers.md)
- [Erneutes Hosten von Designern](./samples/designer-rehosting.md)
