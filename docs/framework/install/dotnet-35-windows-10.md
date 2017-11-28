---
title: Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8
description: Informationen zum Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8.
author: rlander
ms.author: mairaw
keywords: .Net Framework, installieren
ms.date: 05/26/2017
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 67cda1d5-c6g4-4eb5-93e6-4f478de07ff7
ms.openlocfilehash: 85a3cada074714c24015d90c26d94551f4f411f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8

Möglicherweise wird .NET Framework 3.5 zum Ausführen einer App auf Windows 10, Windows 8.1 und Windows 8 benötigt. Sie können diese Schritte auch für frühere Versionen von Windows verwenden.

## <a name="install-the-net-framework-35-on-demand"></a>Installieren von .NET Framework 3.5 bei Bedarf

Wenn Sie versuchen, eine App auszuführen, die .NET Framework 3.5 erfordert, wird möglicherweise das folgende Konfigurationsdialogfeld angezeigt. Wählen Sie **Feature installieren** aus, um .NET Framework 3.5 zu aktivieren. Für diese Option ist eine Internetverbindung erforderlich.

![Dialogfeld für die Installation .NET Framework](./media/dotnet-framework-installation-dialog.jpg)

## <a name="enable-the-net-framework-35-in-control-panel"></a>Aktivieren von .NET Framework 3.5 in der Systemsteuerung

Sie können .NET Framework 3.5 auch über die Systemsteuerung aktivieren. Für diese Option ist eine Internetverbindung erforderlich.

1. Drücken Sie die Windows-Taste ![Windows-Logo](https://i-msdn.sec.s-msft.com/dynimg/IC721376.jpeg) auf der Tastatur, geben Sie „Windows-Funktionen“ ein, und drücken Sie EINGABETASTE. Das Dialogfeld **Windows-Funktionen ein- oder ausschalten** erscheint.

2. Aktivieren Sie das Kontrollkästchen **.NET Framework 3.5 (umfasst .NET 2.0 und 3.0)**, klicken Sie auf **OK**, und starten Sie den Computer neu, wenn Sie dazu aufgefordert werden.

   ![Installieren von .NET über die Systemsteuerung](./media/dotnet-control-panel.png)

   Sie müssen die untergeordneten Elemente für die **HTTP-Aktivierung von Windows Communication Foundation (WCF)** und die **Nicht-HTTP-Aktivierung von Windows Communication Foundation (WCF)** nicht auswählen, es sei denn, Sie sind ein Entwickler oder Serveradministrator und benötigen diese Funktionen.
