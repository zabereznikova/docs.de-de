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
ms.openlocfilehash: f2388f091278d398b5e8f3b82f147ab69937f2aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689522"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Unterschiede zwischen Eigenschaften und Variablen in Visual Basic
Variablen und Eigenschaften, die sowohl Werte darzustellen, die Sie zugreifen können. Es gibt jedoch Unterschiede in den Speicher und Implementierung.  
  
## <a name="variables"></a>Variablen  
 Ein *Variable* direkt auf einen Speicherbereich entspricht. Sie definieren eine Variable mit einer einzigen Deklaration-Anweisung. Kann eine Variable sein. eine *lokale Variable*, innerhalb einer Prozedur und verfügbar nur in dieser Prozedur definiert, oder sie können eine *Membervariable*, definiert in einem Modul, Klasse oder Struktur, jedoch nicht innerhalb einer die Prozedur. Eine Membervariable wird auch bezeichnet ein *Feld*.  
  
## <a name="properties"></a>Eigenschaften  
 Ein *Eigenschaft* ist ein Datenelement für ein Modul, Klasse oder Struktur definiert. Definieren Sie eine Eigenschaft mit einem Codeblock zwischen der `Property` und `End Property` Anweisungen. Der Codeblock enthält eine `Get` Verfahren einen `Set` -Prozedur oder beides. Diese Prozeduren werden aufgerufen, *Eigenschaftenprozeduren* oder *Eigenschaftenaccessoren*. Zusätzlich zum Abrufen oder speichern den Wert der Eigenschaft, können sie auch benutzerdefinierte Aktionen, z. B. ein Indikator für den Zugriff aktualisieren ausführen.  
  
## <a name="differences"></a>Unterschiede  
 Die folgende Tabelle zeigt einige wichtige Unterschiede zwischen Variablen und Eigenschaften.  
  
|Unterschied|Variable|Eigenschaft|  
|-------------------------|--------------|--------------|  
|Deklaration|Einzelne Declaration-Anweisung|Reihe von Anweisungen in einem Codeblock|  
|Implementierung|Zentralen Speicherort|Ausführbarer Code (Eigenschaftenprozeduren)|  
|Speicher|Direkt zugeordnet und Wert der Variablen|In der Regel hat internen Speicher außerhalb der Eigenschaft enthaltende Klasse oder das Modul nicht verfügbar.<br /><br /> Eigenschaftswert nicht existiert oder als gespeicherte Element <sup>1</sup>|  
|Ausführbarer code|Keine|Müssen mindestens eine Prozedur|  
|Lese- und Schreibzugriff|Lese-/Schreibzugriff oder schreibgeschützten|Lese-/Schreibzugriff, schreibgeschützt oder lesegeschützt|  
|Benutzerdefinierte Aktionen (zusätzlich zum Akzeptieren oder Wert zurückgibt)|Nicht möglich|Kann als Teil des festlegen oder Abrufen des Eigenschaftswerts ausgeführt werden|  
  
 <sup>1</sup> im Gegensatz zu einer Variablen, entspricht der Wert einer Eigenschaft kann nicht direkt auf ein einzelnes Element des Speichers. Der Speicher kann für die der Einfachheit halber oder die Sicherheitsgruppe in Teile aufgeteilt werden, oder der Wert kann in verschlüsselter Form gespeichert werden. In diesen Fällen die `Get` -Prozedur Bestandteile zusammen oder entschlüsselt den gespeicherten Wert, und die `Set` -Prozedur den neuen Wert zu verschlüsseln oder Teilen Sie es in den zugehörigen Speicher. Ein Eigenschaftswert möglicherweise flüchtig und wie die Zeit des Tages, in diesem Fall die `Get` Prozedur berechnet es im laufenden Betrieb jedes Mal, die Sie Zugriff auf die Eigenschaft.  
  
## <a name="see-also"></a>Siehe auch
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Vorgehensweise: Erstellen Sie eine Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
