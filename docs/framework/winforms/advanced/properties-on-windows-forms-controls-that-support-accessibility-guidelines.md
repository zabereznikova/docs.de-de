---
title: Eigenschaften für Windows Forms-Steuerelemente, die Richtlinien für Eingabehilfen unterstützen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: b466dcf42561d8ced7b224215538a807c94b174b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524487"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Eigenschaften für Windows Forms-Steuerelemente, die Richtlinien für Eingabehilfen unterstützen
In der standard-Toolbox für Windows Forms-Steuerelemente unterstützen viele der Richtlinien für Eingabehilfen, einschließlich Verfügbarmachung des Tastaturfokus und das Verfügbarmachen von der Bildschirmelemente.  
  
## <a name="planning-ahead-for-accessibility"></a>Vorausplanen für Eingabehilfen  
 Die Eigenschaften des Steuerelements können verwendet werden, um andere Richtlinien für Eingabehilfen unterstützen, wie in der folgenden Tabelle gezeigt. Darüber hinaus sollten Sie die Menüs verwenden, um Zugriff auf das Programmieren von Funktionen bereitzustellen.  
  
|Eigenschaft ""|Überlegungen für Eingabehilfen|  
|----------------------|--------------------------------------|  
|AccessibleDescription|Die Beschreibung ist z. B. die Bildschirmsprachausgabe Eingabehilfen gemeldet. Eingabehilfen sind spezielle Programme und Geräte, die es Personen mit Behinderungen ermöglichen, einen Computer effizienter zu nutzen.|  
|AccessibleName|Der Name, die an die Eingabehilfen gemeldet werden.|  
|AccessibleRole|Beschreibt die Verwendung des Elements in der Benutzeroberfläche.|  
|TabIndex|Erstellt einen logischen Navigationspfad über das Formular. Es ist wichtig für Steuerelemente ohne systeminterne Bezeichnung, z. B. Textfelder, deren zugeordnete Bezeichnung, die in der Aktivierreihenfolge direkt vorangestellt haben.|  
|Text|Verwenden Sie das Zeichen "&", um Zugriffstasten zu erstellen. Mithilfe von Zugriffsschlüsseln ist Teil der Bereitstellung von dokumentierten tastaturzugriffen auf Funktionen.|  
|Schriftgrad|Wenn der Schriftgrad nicht anpassbar ist, sollte klicken sie auf 10 Punkt oder größer festgelegt werden. Sobald Schriftgrad des Formulars festgelegt ist, werden alle in das Formular anschließend hinzugefügten Steuerelemente dieselbe Größe aufweisen.|  
|Forecolor|Wenn diese Eigenschaft auf den Standardwert festgelegt ist, werden die Farbe der benutzereinstellungen auf dem Formular verwendet werden.|  
|Backcolor|Wenn diese Eigenschaft auf den Standardwert festgelegt ist, werden die Farbe der benutzereinstellungen auf dem Formular verwendet werden.|  
|BackgroundImage|Lassen Sie diese Eigenschaft leer, um Text besser lesbar zu machen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows-basierten Anwendungen](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)
