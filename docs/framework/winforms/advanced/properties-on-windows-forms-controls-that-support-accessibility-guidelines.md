---
title: Barrierefreiheits Eigenschaften für Steuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743426"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>Eigenschaften für Windows Forms-Steuerelemente, die Richtlinien für Eingabehilfen unterstützen
Steuerelemente in der Standard Toolbox für Windows Forms unterstützen viele der Richtlinien für Barrierefreiheit, einschließlich der Offenlegung des Tastaturfokus und der Bereitstellung der Bildschirmelemente.  
  
## <a name="planning-ahead-for-accessibility"></a>Vorausplanung für Barrierefreiheit  
 Die Eigenschaften der Steuerelemente können verwendet werden, um andere Barrierefreiheits Richtlinien zu unterstützen, wie in der folgenden Tabelle gezeigt. Außerdem sollten Sie Menüs verwenden, um den Zugriff auf Programm Features zu ermöglichen.  
  
|Control-Eigenschaft|Überlegungen zur Barrierefreiheit|  
|----------------------|--------------------------------------|  
|AccessibleDescription|Die Beschreibung wird den Barrierefreiheits Hilfen (z. b. Bildschirmlesern) gemeldet. Eingabehilfen sind spezielle Programme und Geräte, die es Personen mit Behinderungen ermöglichen, einen Computer effizienter zu nutzen.|  
|AccessibleName|Der Name, der den Barrierefreiheits Hilfen gemeldet wird.|  
|AccessibleRole|Beschreibt die Verwendung des-Elements in der Benutzeroberfläche.|  
|TabIndex|Erstellt einen sinnvollen Navigationspfad über das Formular. Es ist wichtig, dass Steuerelemente ohne intrinsische Bezeichnungen, wie z. b. Textfelder, ihre zugehörige Bezeichnung unmittelbar in der Aktivier Reihenfolge voranstellen.|  
|Text|Verwenden Sie das Zeichen "&", um Zugriffsschlüssel zu erstellen. Die Verwendung von Zugriffs Schlüsseln ist Teil der Bereitstellung dokumentierten Tastatur Zugriffs auf Funktionen.|  
|Schriftgrad|Wenn die Schriftgröße nicht anpassbar ist, sollte Sie auf 10 Punkte oder größer festgelegt werden. Nachdem die Schriftgröße des Formulars festgelegt wurde, haben alle dem Formular hinzugefügten Steuerelemente dieselbe Größe.|  
|Forecolor|Wenn diese Eigenschaft auf den Standardwert festgelegt ist, werden die Farbeinstellungen des Benutzers im Formular verwendet.|  
|Backcolor|Wenn diese Eigenschaft auf den Standardwert festgelegt ist, werden die Farbeinstellungen des Benutzers im Formular verwendet.|  
|BackgroundImage|Lassen Sie diese Eigenschaft leer, damit der Text besser lesbar ist.|  
  
## <a name="see-also"></a>Siehe auch

- [Exemplarische Vorgehensweise: Erstellen von behindertengerechten Windows-basierten Anwendungen](walkthrough-creating-an-accessible-windows-based-application.md)
