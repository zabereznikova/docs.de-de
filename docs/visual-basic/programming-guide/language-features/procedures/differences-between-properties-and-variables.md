---
title: Unterschiede zwischen Eigenschaften und Variablen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
ms.openlocfilehash: 126e4baa2752ba7ccb5e8ff7b06a44839c1d0af2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Unterschiede zwischen Eigenschaften und Variablen in Visual Basic
Variablen und Eigenschaften, die beide Werte darzustellen, die Sie zugreifen können. Es gibt jedoch Unterschiede in den Speicher und die Implementierung.  
  
## <a name="variables"></a>Variablen  
 Ein *Variable* direkt auf einen Speicherbereich entspricht. Sie definieren eine Variable mit einer einzigen Deklaration-Anweisung. Eine Variable kann eine *lokale Variable*, definiert innerhalb einer Prozedur und nur innerhalb der Prozedur verfügbar, oder es kann eine *Membervariable*, definiert in einem Modul, Klasse oder Struktur jedoch nicht innerhalb einer die Prozedur. Eine Membervariable wird auch bezeichnet eine *Feld*.  
  
## <a name="properties"></a>Eigenschaften  
 Ein *Eigenschaft* ist ein Datenelement für ein Modul, Klasse oder Struktur definiert. Definieren Sie eine Eigenschaft einen Codeblock zwischen den `Property` und `End Property` Anweisungen. Der Codeblock enthält eine `Get` Prozedur, eine `Set` Prozedur oder beides. Diese Prozeduren werden aufgerufen, *Eigenschaftenprozeduren* oder *Eigenschaftenaccessoren*. Zusätzlich zum Abrufen oder den Wert der Eigenschaft speichern, können sie auch benutzerdefinierte Aktionen, wie das Aktualisieren von eines Leistungsindikators Zugriff ausführen.  
  
## <a name="differences"></a>Unterschiede  
 Die folgende Tabelle zeigt einige wichtige Unterschiede zwischen Variablen und Eigenschaften.  
  
|Unterschied|Variable|Eigenschaft|  
|-------------------------|--------------|--------------|  
|Deklaration|Einzelne deklarationsanweisung|Reihe von Anweisungen in einem Codeblock|  
|Implementierung|Einziger Speicherort|Ausführbarer Code (Eigenschaftenprozeduren)|  
|Speicher|Direkt zugeordnet und des Variablenwerts|In der Regel hat internen Speicher außerhalb der Eigenschaft enthaltende Klasse oder das Modul nicht verfügbar.<br /><br /> Den Wert der Eigenschaft möglicherweise existiert oder nicht als gespeicherte Element <sup>1</sup>|  
|Ausführbarer code|Keiner|Benötigen Sie mindestens eine Prozedur|  
|Lese- und Schreibzugriff|Lese-/Schreibzugriff oder schreibgeschützt|Lese-/Schreibzugriff, schreibgeschützt oder lesegeschützt|  
|Benutzerdefinierte Aktionen (zusätzlich zum Akzeptieren oder zurückgeben Wert)|Nicht möglich|Kann als Teil des festlegen oder Abrufen des Eigenschaftswerts ausgeführt werden|  
  
 <sup>1</sup> im Gegensatz zu einer Variablen der Wert einer Eigenschaft entsprechen möglicherweise nicht direkt auf ein einzelnes Element des Speichers. Der Speicher möglicherweise für Komfort und Sicherheit in Teile aufgeteilt werden, oder der Wert kann in verschlüsselter Form gespeichert werden. In diesen Fällen die `Get` -Prozedur die Abschnitte zusammen oder entschlüsselt den gespeicherten Wert und die `Set` -Prozedur den neuen Wert zu verschlüsseln oder Teilen Sie es in das Speicherelement. Ein Eigenschaftswert kann in diesem Fall kurzlebigen, wie die Zeit des Tages, werden die `Get` Prozedur würde berechnen sie bei Bedarf jedes Mal, die Sie Zugriff auf die Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)  
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)  
 [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)  
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
