---
title: Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: 57abf3527af146f1ce918bcabbc6a5a34bfb9b34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222327"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement
Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement bietet leistungsstarke Layout-Funktionen, die Sie sorgfältig berücksichtigen sollten, bevor Sie in Windows Forms verwenden.  
  
## <a name="recommendations"></a>Empfehlungen  
 Die folgenden Empfehlungen können Sie verwenden die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement seine optimal nutzen.  
  
### <a name="targeted-use"></a>Gezielte verwenden  
 Verwenden der <xref:System.Windows.Forms.TableLayoutPanel> nur selten zu steuern. Sie sollten nicht es in allen Situationen verwenden, die ein Layout mit veränderbarer Größe erfordern. Die folgende Liste beschreibt die Layouts, mit denen am meisten von der Verwendung von profitieren die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement:  
  
-   Layouts, in denen es sind mehrere Teile des Formulars, die proportional zueinander zu vergrößern.  
  
-   Layouts, die dynamisch generiert, zur Laufzeit, wie z. B. Dateneingabeformularen, die anpassbaren Felder hinzugefügt oder entfernt oder geändert werden, basierend auf Einstellungen.  
  
-   Layouts, mit die auf eine gesamte feste Größe beibehalten werden sollen. Z. B. möglicherweise ein Dialogfeld an, die kleiner als 800 x 600 beibehalten werden sollen, aber Sie lokalisierte Zeichenfolgen unterstützen müssen.  
  
 Die folgende Liste beschreibt die Layouts, die von der Verwendung nicht besonders sinnvoll ist die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement:  
  
-   Einfachen Dateneingabeformularen mit einer einzelnen Spalte von Bezeichnungen und einer einzelnen Spalte des Texteingabe Bereiche.  
  
-   Formulare mit einem einzelnen großen anzeigen Bereich, der gesamte verfügbaren Platz ausfüllen soll, bei einer Größenänderung. Ein Beispiel hierfür ist eine Form, die eine einzelne zeigt <xref:System.Windows.Forms.PropertyGrid> Steuerelement. In diesem Fall verwenden Sie verankern, da nichts erweitert werden soll, wenn die Größe des Formulars geändert wird.  
  
 Wählen Sie sorgfältig, welche Steuerelemente müssen sich in einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Wenn Sie über genügend Platz für den Text 30 % Verankerung Wachstum verfügen, sollten Sie verwenden die <xref:System.Windows.Forms.Control.Anchor%2A> nur-Eigenschaft. Wenn Sie den Speicherplatz, der das Layout erforderliche einschätzen können, verwenden Sie <xref:System.Windows.Forms.Control.Dock%2A> und <xref:System.Windows.Forms.Control.Anchor%2A> ist einfacher als die Details des verbleibenden Speicherplatzes schätzen und <xref:System.Windows.Forms.Control.AutoSize%2A> Verhalten.  
  
 Im Allgemeinen ist beim Entwerfen des Layouts mit den <xref:System.Windows.Forms.TableLayoutPanel> steuern, den Entwurf so einfach wie möglich zu halten.  
  
### <a name="use-the-document-outline-window"></a>Verwenden Sie die Dokumentgliederung (Fenster)  
 Das Fenster "Dokumentgliederung" bietet Ihnen eine Strukturansicht der das Layout, die Sie verwenden können, um die Z-Reihenfolge und über-und untergeordnete Beziehungen der Steuerelemente zu bearbeiten. Von der **Menü "Ansicht"** Option **Other Windows**, und wählen Sie dann **Dokumentgliederung**.  
  
### <a name="avoid-nesting"></a>Vermeiden Sie die Schachtelung  
 Vermeiden Sie andere Schachtelung <xref:System.Windows.Forms.TableLayoutPanel> -Steuerelementen innerhalb einer <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Geschachtelte Layouts Debuggen kann schwierig sein.  
  
### <a name="avoid-visual-inheritance"></a>Visuellen Vererbung vermeiden  
 Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement visuellen Vererbung in der Windows Forms-Designer nicht unterstützt. Ein <xref:System.Windows.Forms.TableLayoutPanel> als zur Entwurfszeit "gesperrt"-Steuerelement in einer abgeleiteten Klasse angezeigt wird.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
