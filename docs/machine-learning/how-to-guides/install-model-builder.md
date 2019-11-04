---
title: Installieren des Modell-Generators
description: Erfahren Sie, wie Sie das ML.NET-Modell-Generator-Tool installieren.
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: a1034d294012b8df5ec778fc40602fe52223961d
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774567"
---
# <a name="how-to-install-mlnet-model-builder"></a>Installieren des ML.NET-Modell-Generators

Erfahren Sie, wie Sie den ML.NET-Modell-Generator installieren, um Ihre .NET-Anwendungen mit maschinellem Lernen zu erweitern.

> [!NOTE]
> Der Modell-Generator befindet sich derzeit in der Vorschauphase.

## <a name="pre-requisites"></a>Voraussetzungen

- Visual Studio 2017 Version 15.9.12 oder höher/Visual Studio 2019
- .NET Core 2.1 oder ein höheres SDK

## <a name="limitations"></a>Einschränkungen

- Die Erweiterung für den ML.NET-Modell-Generator funktioniert zurzeit nur in Visual Studio für Windows.
- Die Größe des Trainingsdatasets ist auf 1 GB beschränkt.
- Für SQL Server gilt ein Grenzwert von 100.000 Zeilen für das Training.
- Microsoft SQL Server Data Tools für Visual Studio 2017 wird nicht unterstützt.

## <a name="install"></a>Installieren

Der ML.NET-Modell-Generator kann entweder über den Visual Studio Marketplace oder aus Visual Studio heraus installiert werden.

### <a name="visual-studio-marketplace"></a>Visual Studio Marketplace

1. Herunterladen vom [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)
1. Befolgen Sie die Anweisungen zur Installation auf der jeweiligen Visual Studio-Version.

### <a name="visual-studio-2017"></a>Visual Studio 2017

1. Klicken Sie in der Menüleiste auf **Tools** > **Erweiterungen und Updates**.

    ![VS2017-Dialogfeld zum Öffnen des Erweiterungs-Managers](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. Wählen Sie in der Anzeige *Erweiterungen und Updates* den *Onlineknoten* aus.
1. Suchen Sie in der Suchleiste nach *ML.NET-Modell-Generator*, und wählen Sie in den Ergebnissen „ML.NET-Modell-Generator (Vorschauversion)“ aus.

    ![VS2017-Dialogfeld zum Suchen und Installieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2017-install-model-builder.png)

1. Folgen Sie den Anweisungen, um die Installation abzuschließen.

### <a name="visual-studio-2019"></a>Visual Studio 2019

1. Wählen Sie in der Menüleiste **Erweiterungen** > **Erweiterungen verwalten** aus.

    ![VS2019-Dialogfeld zum Öffnen des Erweiterungs-Managers](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. Wählen Sie in der Anzeige *Erweiterungen und Updates* den *Onlineknoten* aus.
1. Geben Sie in die Suchleiste *ML.NET-Modell-Generator* ein, und wählen Sie „ML.NET-Modellgenerator (Vorschauversion)“ aus.

    ![VS2019-Dialogfeld zum Suchen und Installieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2019-install-model-builder.png)

1. Folgen Sie den Anweisungen, um die Installation abzuschließen.

## <a name="uninstall"></a>Deinstallieren

### <a name="visual-studio-2017"></a>Visual Studio 2017

1. Wählen Sie in der Menüleiste **Tools** > **Erweiterungen und Updates** aus.

    ![VS2017-Dialogfeld zum Öffnen der Verwaltungserweiterungen](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. Erweitern Sie innerhalb der Eingabeaufforderung *Erweiterung und Updates* den Knoten *Installiert*, und wählen Sie *Tools* aus.
1. Wählen Sie in der Liste der Tools „ML.NET-Modell-Generator“ (Vorschauversion) aus und dann *Deinstallieren*.

    ![VS2017-Dialogfeld zum Suchen und Deinstallieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. Folgen Sie den Anweisungen, um die Deinstallation abzuschließen.

### <a name="visual-studio-2019"></a>Visual Studio 2019

1. Wählen Sie in der Menüleiste **Erweiterungen** > **Erweiterungen verwalten** aus.

    ![VS2019-Dialogfeld zum Öffnen der Verwaltungserweiterungen](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. Erweitern Sie innerhalb der Eingabeaufforderung *Erweiterung und Updates* den Knoten *Installiert*, und wählen Sie *Tools* aus.
1. Wählen Sie in der Liste der Tools „ML.NET-Modell-Generator“ (Vorschauversion) aus und dann *Deinstallieren*.

    ![VS2019-Dialogfeld zum Suchen und Deinstallieren der Modell-Generator-Erweiterung im Erweiterungs-Manager](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. Folgen Sie den Anweisungen, um die Deinstallation abzuschließen.

## <a name="upgrade"></a>Upgrade

Der Upgradevorgang ähnelt dem Installationsvorgang. Laden Sie entweder die neueste Version vom Visual Studio Marketplace herunter oder verwenden Sie den Erweiterungs-Manager in Visual Studio.
