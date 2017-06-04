---
title: "Empfohlene Vorgehensweisen f&#252;r das TableLayoutPanel-Steuerelement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "Automatische Größenanpassung"
  - "AutoSize-Eigenschaft, TableLayoutPanel-Steuerelement"
  - "Bewährte Methoden, TableLayoutPanel-Steuerelement"
  - "Steuerelemente [Windows Forms], Größe anpassen"
  - "Formulare, Bewährte Methoden"
  - "Layout [Windows Forms]"
  - "Layout [Windows Forms], Bewährte Methoden"
  - "Layout [Windows Forms], AutoSize"
  - "Größe anpassen, Automatisch"
  - "TableLayoutPanel-Steuerelement [Windows Forms], Bewährte Methoden"
  - "TableLayoutPanel-Steuerelement [Windows Forms], AutoSize-Verhalten"
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Empfohlene Vorgehensweisen f&#252;r das TableLayoutPanel-Steuerelement
Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement bietet leistungsstarke Layoutfeatures, über die Sie genau Bescheid wissen sollten, bevor Sie sie in Windows Forms verwenden.  
  
## Empfehlungen  
 Die folgenden Empfehlungen helfen Ihnen, das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement optimal zu verwenden.  
  
### Beabsichtigte Verwendung  
 Verwenden Sie das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement nur begrenzt.  Sie sollten es nicht in allen Situationen verwenden, die ein in der Größe veränderbares Layout erfordern.  In der folgenden Liste werden Layouts beschrieben, bei denen die Verwendung des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements am sinnvollsten ist:  
  
-   Layouts, in denen mehrere Teile des Formulars proportional zueinander angepasst werden.  
  
-   Layouts, die zur Laufzeit geändert oder dynamisch generiert werden, z. B. Dateneingabeformulare, zu denen vom Benutzer anpassbare Felder auf Wunsch hinzugefügt bzw. aus diesen entfernt werden können.  
  
-   Layouts, deren Größe insgesamt gleich bleiben sollte.  Möglicherweise verfügen Sie z. B. über ein Dialogfeld, das kleiner bleiben soll als 800 x 600, aber lokalisierte Zeichenfolgen unterstützen soll.  
  
 In der folgenden Liste werden Layouts beschrieben, bei denen die Verwendung des <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelements nicht besonders sinnvoll ist:  
  
-   Einfache Dateneingabeformulare mit einer einzelnen Spalte von Bezeichnungen und einer einzelnen Spalte von Texteingabebereichen.  
  
-   Formulare mit einem einzelnen großen Anzeigebereich, der bei einer Größenanpassung den verfügbaren Platz ausfüllen sollte.  Ein Beispiel hierfür ist ein Formular, in dem ein einzelnes <xref:System.Windows.Forms.PropertyGrid>\-Steuerelement angezeigt wird.  In diesem Fall sollten Sie die Verankerung verwenden, da außer der Größe des Formulars nichts verändert werden soll.  
  
 Überlegen Sie genau, welche Steuerelemente in einem <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement benötigt werden.  Wenn der entsprechende Platz zur Verfügung steht, um den Text durch Verankerung um 30 % zu vergrößern, sollten Sie in Erwägung ziehen, die <xref:System.Windows.Forms.Control.Anchor%2A>\-Eigenschaft zu verwenden.  Wenn sich der für das Layout erforderliche Speicherplatz einschätzen lässt, ist es einfacher, <xref:System.Windows.Forms.Control.Dock%2A> und <xref:System.Windows.Forms.Control.Anchor%2A> zu verwenden, als die Details des verbleibenden Platzes und das <xref:System.Windows.Forms.Control.AutoSize%2A>\-Verhalten einzuschätzen.  
  
 Beim Entwerfen des Layouts mit dem <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement sollte der Entwurf im Allgemeinen so einfach wie möglich gehalten werden.  
  
### Verwenden des Fensters Dokumentgliederung  
 Das Fenster Dokumentgliederung bietet eine Strukturansicht des Layouts, die zum Bearbeiten der Z\-Reihenfolge und der über\- bzw. untergeordneten Beziehungen der Steuerelemente verwendet werden kann.  Wählen Sie im Menü **Ansicht** die Option **Weitere Fenster** und anschließend **Dokumentgliederung** aus.  
  
### Vermeiden von Verschachtelungen  
 Nach Möglichkeit sollten Sie keine anderen <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelemente in einem <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement verschachteln.  Das Debuggen von verschachtelten Layouts kann schwierig sein.  
  
### Vermeiden von visueller Vererbung  
 Das <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement unterstützt keine visuelle Vererbung im Windows Forms\-Designer.  Ein <xref:System.Windows.Forms.TableLayoutPanel>\-Steuerelement in einer abgeleiteten Klasse wird zur Entwurfszeit als "gesperrt" angezeigt.  
  
## Siehe auch  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 <xref:System.Windows.Forms.FlowLayoutPanel>