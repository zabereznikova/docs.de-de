---
title: Übersicht über die ImageList-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ImageList
helpviewer_keywords:
- collection controls [Windows Forms], images
- icon list control
- ImageList component [Windows Forms], about ImageList component
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
ms.openlocfilehash: 9869e647613ccf009954a5d65445947fbced40e7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57709843"
---
# <a name="imagelist-component-overview-windows-forms"></a>Übersicht über die ImageList-Komponente (Windows Forms)

Die <xref:System.Windows.Forms.ImageList>-Komponente in Windows Forms wird zum Speichern von Bildern verwendet, die dann von Steuerelementen angezeigt werden können. Mit einer Bildliste können Sie Code für einen einzelnen, konsistenten Katalog von Bildern schreiben. So können z. B. Bilder, die durch ein <xref:System.Windows.Forms.Button>-Steuerelement angezeigt werden, gedreht werden, indem einfach die <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A>- oder <xref:System.Windows.Forms.ButtonBase.ImageKey%2A>-Eigenschaft der Schaltfläche geändert wird. Dieselbe Bildliste kann auch mit mehreren Steuerelementen verbunden werden. Wenn z. B. sowohl ein <xref:System.Windows.Forms.ListView>-Steuerelement als auch ein <xref:System.Windows.Forms.TreeView>-Steuerelement verwendet werden, um dieselbe Liste von Dateien anzuzeigen, bewirkt eine Änderung des Dateisymbols in der Bildliste, dass das neue Symbol in beiden Ansichten angezeigt wird.

## <a name="using-imagelist-with-controls"></a>Verwenden von ImageList mit Steuerelementen

Eine Bildliste kann mit jedem Steuerelement eingesetzt werden, das eine `ImageList`-Eigenschaft aufweist. Wenn jedoch ein <xref:System.Windows.Forms.ListView>-Steuerelement verwendet wird, muss dieses eine <xref:System.Windows.Forms.ListView.SmallImageList%2A>-Eigenschaft und eine <xref:System.Windows.Forms.ListView.LargeImageList%2A>-Eigenschaft aufweisen. Die folgenden Steuerelemente können mit einer Bildliste verbunden werden: <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> und <xref:System.Windows.Forms.Label>. Legen Sie die `ImageList`-Eigenschaft des Steuerelements auf den Namen der <xref:System.Windows.Forms.ImageList>-Komponente fest, um die Bildliste einem Steuerelement zuzuordnen.

## <a name="key-properties"></a>Schlüsseleigenschaften

Die wichtigste Eigenschaft der <xref:System.Windows.Forms.ImageList>-Komponente ist <xref:System.Windows.Forms.ImageList.Images%2A>, in der die Bilder enthalten sind, die vom zugeordneten Steuerelement verwendet werden. Der Zugriff auf jedes einzelne Bild kann über dessen Indexwert oder dessen Schlüssel erfolgen. Mit der <xref:System.Windows.Forms.ImageList.ColorDepth%2A>-Eigenschaft wird die Anzahl der Farben bestimmt, mit denen die Bilder dargestellt werden. Alle Bilder werden in derselben Größe angezeigt, die durch die <xref:System.Windows.Forms.ImageList.ImageSize%2A>-Eigenschaft festgelegt ist. Größere Bilder werden entsprechend angepasst.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ImageList>
- [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der ImageList-Komponente in Windows Forms](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)