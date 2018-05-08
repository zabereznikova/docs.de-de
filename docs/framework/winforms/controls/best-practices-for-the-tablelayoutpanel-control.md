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
ms.openlocfilehash: 40322dc6c5facd4167a4c9ac5c12fdf2a8831b7c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>Empfohlene Vorgehensweisen für das TableLayoutPanel-Steuerelement
Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement umfasst leistungsstarke Layout-Funktionen, die Sie sorgfältig berücksichtigen sollten, bevor Sie in Windows Forms verwenden.  
  
## <a name="recommendations"></a>Empfehlungen  
 Die folgenden Empfehlungen können Sie verwenden die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement, um die besten davon profitieren.  
  
### <a name="targeted-use"></a>Zielgruppe  
 Verwenden der <xref:System.Windows.Forms.TableLayoutPanel> nur selten zu steuern. Sie sollten nicht in allen Situationen verwendet, die in der Größe veränderbaren Layout erfordern. Die folgende Liste beschreibt Layouts, mit denen am meisten von der Verwendung von profitieren die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement:  
  
-   Layouts, in denen es sind mehrere Teile des Formulars, die proportional zueinander zu vergrößern.  
  
-   Layouts, mit die generiert dynamisch zur Laufzeit, z. B. Dateneingabeformulare, denen Benutzer anpassbare Felder hinzugefügt oder entfernt oder geändert werden, basierend auf Einstellungen.  
  
-   Layouts, die an einem festen Gesamtgröße bleiben soll. Beispielsweise müssen unter Umständen einen (Dialogfeld), der kleiner als 800 x 600 bleiben soll, aber Sie lokalisierte Zeichenfolgen unterstützen müssen.  
  
 Die folgende Liste beschreibt Layouts, mit denen nicht erheblich von der Verwendung gilt die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement:  
  
-   Einfache Dateneingabeformulare mit einer einzelnen Spalte von Bezeichnungen und einer einzelnen Spalte Texteingabe Bereiche.  
  
-   Formulare mit einem einzelnen großen anzeigen Bereich, der alle verfügbaren Platz ausfüllen soll, tritt eine Größe Ein Beispiel hierfür ist ein Formular, das ein einzelnes zeigt <xref:System.Windows.Forms.PropertyGrid> Steuerelement. In diesem Fall verwenden Sie verankern, da nichts erweitert werden soll, wenn die Größe des Formulars.  
  
 Wählen Sie sorgfältig, welche Steuerelemente müssen in einem <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Wenn Sie ausreichend Platz für den Text 30 % Verankerung vergrößert haben, können Sie verwenden die <xref:System.Windows.Forms.Control.Anchor%2A> nur-Eigenschaft. Verwenden Sie das Layout erforderlichen Speicherplatzes nicht abschätzen können, <xref:System.Windows.Forms.Control.Dock%2A> und <xref:System.Windows.Forms.Control.Anchor%2A> ist einfacher als die Details des verbleibenden Speicherplatzes schätzen und <xref:System.Windows.Forms.Control.AutoSize%2A> Verhalten.  
  
 Im Allgemeinen gilt: beim Entwerfen des Layouts mit den <xref:System.Windows.Forms.TableLayoutPanel> steuern, den Entwurf so einfach wie möglich halten.  
  
### <a name="use-the-document-outline-window"></a>Verwenden Sie die Dokumentgliederung (Fenster)  
 Das Fenster "Dokumentgliederung" bietet Ihnen eine Strukturansicht der das Layout, die Sie verwenden können, um die Z-Reihenfolge und über-und untergeordneten Beziehungen zwischen Ihrer Steuerelemente zu bearbeiten. Aus der **Menü "Ansicht"** Option **Weitere Fenster**, und wählen Sie dann **Dokumentgliederung**.  
  
### <a name="avoid-nesting"></a>Vermeiden Sie die Schachtelung  
 Vermeiden Sie die Schachtelung andere <xref:System.Windows.Forms.TableLayoutPanel> steuert innerhalb einer <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement. Debuggen von verschachtelten Layouts kann schwierig sein.  
  
### <a name="avoid-visual-inheritance"></a>Visuellen Vererbung vermeiden  
 Die <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement visuellen Vererbung in Windows Forms-Designer nicht unterstützt. Ein <xref:System.Windows.Forms.TableLayoutPanel> Steuerelement in einer abgeleiteten Klasse wird angezeigt, da zur Entwurfszeit "gesperrt".  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
