---
title: Eigenschaften für Windows Forms-Steuerelemente, die Richtlinien für Eingabehilfen unterstützen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: eee7499373809538355227633ab9a1a66aedb9ed
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57716399"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Eigenschaften für Windows Forms-Steuerelemente, die Richtlinien für Eingabehilfen unterstützen
Steuerelemente auf der standard-Toolbox für Windows Forms unterstützen viele Barrierefreiheits-Richtlinien, einschließlich Verfügbarmachung des Tastaturfokus und die Bildschirmelementen verfügbar zu machen.  
  
## <a name="planning-ahead-for-accessibility"></a>Vorausplanung für den Zugriff auf  
 Die Eigenschaften des Steuerelements können verwendet werden, um weitere Richtlinien für Barrierefreiheit zu unterstützen, wie in der folgenden Tabelle gezeigt. Darüber hinaus sollten Sie die Menüs verwenden, um Zugriff auf das Programmieren von Funktionen bereitzustellen.  
  
|Eigenschaft des Steuerelements|Überlegungen zur Barrierefreiheit|  
|----------------------|--------------------------------------|  
|AccessibleDescription|Die Beschreibung ist auf Barrierefreiheit-Hilfsmittel, wie z.B. Sprachausgabe gemeldet. Eingabehilfen sind spezielle Programme und Geräte, die es Personen mit Behinderungen ermöglichen, einen Computer effizienter zu nutzen.|  
|AccessibleName|Der Name, der an die Eingabehilfen gemeldet wird.|  
|AccessibleRole|Beschreibt die Verwendung des Elements in der Benutzeroberfläche.|  
|TabIndex|Erstellt einen logischen Navigationspfad durch das Formular an. Es ist wichtig für Steuerelemente ohne systeminterne Bezeichnung, z. B. Textfelder, damit die zugeordnete Bezeichnung, die in der Aktivierreihenfolge direkt vorangestellt.|  
|Text|Verwenden Sie das Zeichen "&", um Zugriffstasten zu erstellen. Mithilfe von Zugriffsschlüsseln ist Teil der Bereitstellung von dokumentierten tastaturzugriffen auf Features.|  
|Schriftgrad|Wenn der Schriftgrad nicht anpassbar ist, sollte dann sie auf 10 Punkt oder größer festgelegt werden. Nach der Schriftgrad des Formulars festgelegt ist, werden alle Steuerelemente zum Formular hinzugefügt wurde, danach die gleiche Größe aufweisen.|  
|Forecolor|Wenn diese Eigenschaft auf den Standardwert festgelegt ist, werden die Farbe von benutzereinstellungen auf dem Formular verwendet werden.|  
|Backcolor|Wenn diese Eigenschaft auf den Standardwert festgelegt ist, werden die Farbe von benutzereinstellungen auf dem Formular verwendet werden.|  
|BackgroundImage|Lassen Sie diese Eigenschaft leer, um den Text lesbarer zu gestalten.|  
  
## <a name="see-also"></a>Siehe auch
- [Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows-basierten Anwendungen](walkthrough-creating-an-accessible-windows-based-application.md)
