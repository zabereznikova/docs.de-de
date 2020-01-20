---
title: Installieren von .NET Framework 3.5 unter Windows 10, 8.1, 8
description: Informationen zum Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8.
ms.date: 07/16/2018
ms.openlocfilehash: 208016e22eed324a3996552284072c6ad29637a5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716394"
---
# <a name="install-the-net-framework-35-on-windows-10-windows-81-and-windows-8"></a>Installieren von .NET Framework 3.5 auf Windows 10, Windows 8.1 und Windows 8

Möglicherweise wird .NET Framework 3.5 zum Ausführen einer App auf Windows 10, Windows 8.1 und Windows 8 benötigt. Sie können diese Schritte auch für frühere Versionen von Windows verwenden.

## <a name="install-the-net-framework-35-on-demand"></a>Installieren von .NET Framework 3.5 bei Bedarf

Wenn Sie versuchen, eine App auszuführen, die .NET Framework 3.5 erfordert, wird möglicherweise das folgende Konfigurationsdialogfeld angezeigt. Wählen Sie **Feature installieren** aus, um .NET Framework 3.5 zu aktivieren. Für diese Option ist eine Internetverbindung erforderlich.

![Screenshot des Dialogfelds für die Installation von .NET Framework.](./media/dotnet-35-windows-10/dotnet-framework-installation-dialog.png)

### <a name="why-am-i-getting-this-pop-up"></a>Warum wird mir dieses Popup angezeigt?

.NET Framework wurde von Microsoft erstellt und bietet eine Umgebung zur Ausführung von Anwendungen. Es stehen verschiedene Versionen zur Verfügung. Viele Unternehmen entwickeln ihre Apps zur Ausführung mit .NET Framework, und diese Apps sind für eine bestimmte Version entworfen. Wenn Sie dieses Popup sehen, versuchen Sie, eine Anwendung auszuführen, für die .NET Framework 3.5 erforderlich ist, aber diese Version ist auf Ihrem Computer nicht installiert.

## <a name="enable-the-net-framework-35-in-control-panel"></a>Aktivieren von .NET Framework 3.5 in der Systemsteuerung

Sie können .NET Framework 3.5 auch über die Systemsteuerung aktivieren. Für diese Option ist eine Internetverbindung erforderlich.

1. Drücken Sie die WINDOWS-TASTE ![Screenshot des Logos der Windows-Taste.](./media/dotnet-35-windows-10/windows-keyboard-logo.png) auf der Tastatur, geben Sie „Windows-Funktionen“ ein, und drücken Sie die EINGABETASTE. Das Dialogfeld **Windows-Funktionen ein- oder ausschalten** erscheint.

2. Aktivieren Sie das Kontrollkästchen **.NET Framework 3.5 (umfasst .NET 2.0 und 3.0)** , klicken Sie auf **OK**, und starten Sie den Computer neu, wenn Sie dazu aufgefordert werden.

   ![Screenshot, der die Installation von .NET mit der Systemsteuerung zeigt.](./media/dotnet-35-windows-10/dotnet-control-panel.png)

   Sie müssen die untergeordneten Elemente für die **HTTP-Aktivierung von Windows Communication Foundation (WCF)** und die **Nicht-HTTP-Aktivierung von Windows Communication Foundation (WCF)** nicht auswählen, es sei denn, Sie sind ein Entwickler oder Serveradministrator und benötigen diese Funktionen.

## <a name="troubleshoot-the-installation-of-the-net-framework-35"></a>Problembehandlung bei der Installation von .NET Framework 3.5

Während der Installation tritt möglicherweise der Fehler 0x800f0906, 0x800f0907, 0x800f081f oder 0x800F0922 auf. In diesem Fall verwenden Sie die Informationen unter [.NET Framework 3.5-Installationsfehler: 0x800f0906, 0x800f0907 oder 0x800f081f](https://support.microsoft.com/help/2734782/net-framework-3-5-installation-error-0x800f0906--0x800f081f--0x800f09), um zu erfahren, wie Sie diese Probleme beheben können.

Wenn Sie das Installationsproblem weiterhin nicht lösen können oder keine Internetverbindung zur Verfügung steht, können Sie versuchen, die Installation über Ihr Windows-Installationsmedium durchzuführen. Weitere Informationen finden Sie unter [Bereitstellen von .NET Framework 3.5 mit der Abbildverwaltung für die Bereitstellung (DISM)](/windows-hardware/manufacture/desktop/deploy-net-framework-35-by-using-deployment-image-servicing-and-management--dism). Wenn keine Installationsmedien vorhanden sind, lesen Sie [Erstellen eines Installationsmediums für Windows](https://support.microsoft.com/help/15088/windows-create-installation-media).

> [!WARNING]
> Wenn Sie .NET Framework 3.5 nicht über Windows Update installieren, müssen Sie sicherstellen, dass ausschließlich Quellen derselben Windows-Betriebssystemversion verwendet werden. Die Verwendung eines Quellpfads, der nicht derselben Windows-Version entspricht, verhindert nicht, dass eine nicht übereinstimmende Version von .NET Framework 3.5 installiert wird. Dies führt jedoch dazu, dass das System in einem nicht unterstützten und nicht wartbaren Status wechselt.
