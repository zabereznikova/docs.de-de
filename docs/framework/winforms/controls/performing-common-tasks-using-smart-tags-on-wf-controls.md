---
title: Ausführen allgemeiner Aufgaben mit Smarttags für Steuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- DesignerAction object model
- smart tags
- designer actions
ms.assetid: cac337e6-00f6-4584-80f4-75728f5ea113
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 826313d0a89410f62c034a5fba4dee32e90a1750
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744257"
---
# <a name="walkthrough-perform-common-tasks-using-smart-tags"></a>Exemplarische Vorgehensweise: Ausführen allgemeiner Aufgaben mit Smarttags

Wenn Sie Formulare und Steuerelemente für Ihre Windows Forms-Anwendung erstellen, gibt es viele Aufgaben, die Sie wiederholt ausführen werden. Dies sind einige der häufig ausgeführten Aufgaben, die Sie ausführen werden:

- Hinzufügen oder Entfernen einer Registerkarte auf einem <xref:System.Windows.Forms.TabControl>.

- Andocken eines Steuer Elements an das übergeordnete Element.

- Ändern der Ausrichtung eines <xref:System.Windows.Forms.SplitContainer> Steuer Elements.

Um die Entwicklung zu beschleunigen, bieten viele Steuerelemente Smarttags, bei denen es sich um Kontextbezogene Menüs handelt, mit denen Sie häufige Aufgaben wie diese in einer einzigen Geste zur Entwurfszeit ausführen können. Diese Aufgaben werden als *Smarttag-Verben*bezeichnet.

Smarttags bleiben während ihrer Lebensdauer im Designer an eine Steuerelement Instanz angefügt und sind immer verfügbar.

## <a name="create-the-project"></a>Erstellen des Projekts

Im ersten Schritt wird das Projekt erstellt und das Formular eingerichtet.

1. Erstellen Sie in Visual Studio ein Windows-basiertes Anwendungsprojekt mit dem Namen **SmartTagsExample**.

2. Wählen Sie in der **Windows Forms-Designer**das Formular aus.

## <a name="use-smart-tags"></a>Smarttags verwenden

Smarttags sind immer zur Entwurfszeit für Steuerelemente verfügbar, die Sie bieten.

1. Ziehen Sie eine <xref:System.Windows.Forms.TabControl> aus der **Toolbox** auf das Formular. Beachten Sie das Smarttag-Symbol (![smarttagglyphe](./media/vs-winformsmttagglyph.gif)), das auf der Seite des <xref:System.Windows.Forms.TabControl>angezeigt wird.

2. Klicken Sie auf das Smarttagsymbol. Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Registerkarte hinzufügen** aus. Beachten Sie, dass dem <xref:System.Windows.Forms.TabControl>eine neue Registerkarte hinzugefügt wird.

3. Ziehen Sie ein <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelement aus der **Toolbox** auf das Formular.

4. Klicken Sie auf das Smarttagsymbol. Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **Spalten hinzufügen** aus. Beachten Sie, dass dem <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement eine neue Spalte hinzugefügt wird.

5. Ziehen Sie ein <xref:System.Windows.Forms.SplitContainer> -Steuerelement aus der **Toolbox** auf das Formular.

6. Klicken Sie auf das Smarttagsymbol. Wählen Sie im Kontextmenü, das neben dem Symbol angezeigt wird, das Element **horizontale Splitter Ausrichtung** aus. Beachten Sie, dass die Splitter Leiste des <xref:System.Windows.Forms.SplitContainer> Steuer Elements nun horizontal ausgerichtet ist.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Forms.TextBox>
- <xref:System.Windows.Forms.TabControl>
- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.ComponentModel.Design.DesignerActionList>
