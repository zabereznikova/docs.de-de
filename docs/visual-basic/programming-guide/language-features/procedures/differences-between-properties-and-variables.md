---
title: Unterschiede zwischen Eigenschaften und Variablen
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
ms.openlocfilehash: 162bd71eaebdf55f6be89e0c5dce7acc1b975d79
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403303"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a>Unterschiede zwischen Eigenschaften und Variablen in Visual Basic
Variablen und Eigenschaften stellen Werte dar, auf die Sie zugreifen können. Es gibt jedoch Unterschiede bei der Speicherung und Implementierung.  
  
## <a name="variables"></a>Variables  
 Eine *Variable* entspricht direkt einem Speicherort. Sie definieren eine Variable mit einer einzelnen Deklarations Anweisung. Eine Variable kann eine *lokale Variable*sein, die innerhalb einer Prozedur definiert ist und nur innerhalb dieser Prozedur verfügbar ist. Sie kann auch eine Element *Variable*sein, die in einem Modul, einer Klasse oder einer Struktur definiert ist, aber nicht in einer Prozedur. Eine Member-Variable wird auch als *Feld*bezeichnet.  
  
## <a name="properties"></a>Eigenschaften  
 Eine *Eigenschaft* ist ein Datenelement, das für ein Modul, eine Klasse oder eine Struktur definiert ist. Sie definieren eine Eigenschaft mit einem Codeblock zwischen der `Property` -Anweisung und der- `End Property` Anweisung. Der Codeblock enthält eine `Get` Prozedur, eine `Set` Prozedur oder beides. Diese Prozeduren werden als *Eigenschaften Prozeduren* oder *Eigenschaften Accessoren*bezeichnet. Zusätzlich zum Abrufen oder Speichern des Eigenschafts Werts können auch benutzerdefinierte Aktionen durchgeführt werden, z. b. das Aktualisieren eines Zugriffs Zählers.  
  
## <a name="differences"></a>Unterschiede  
 In der folgenden Tabelle werden einige wichtige Unterschiede zwischen Variablen und Eigenschaften angezeigt.  
  
|Differenz Punkt|Variable|Eigenschaft|  
|-------------------------|--------------|--------------|  
|Deklaration|Single Declaration-Anweisung|Eine Reihe von Anweisungen in einem Codeblock|  
|Implementierung|Einzelner Speicherort|Ausführbarer Code (Eigenschaften Prozeduren)|  
|Storage|Direkt dem Wert der Variablen zugeordnet|In der Regel ist interner Speicher außerhalb der enthaltenden Klasse oder des Moduls der Eigenschaft nicht verfügbar.<br /><br /> Der Eigenschafts Wert ist möglicherweise nicht als gespeicherter Element <sup>1</sup> vorhanden.|  
|Ausführbarer Code|Keine|Mindestens eine Prozedur muss vorhanden sein.|  
|Lese-und Schreibzugriff|Lese-/Schreibzugriff oder schreibgeschützt|Lese-/Schreibzugriff, schreibgeschützt oder schreibgeschützt|  
|Benutzerdefinierte Aktionen (zusätzlich zur Annahme oder Rückgabe von Wert)|Nicht möglich|Kann als Teil der Einstellung oder dem Abrufen des Eigenschafts Werts ausgeführt werden.|  
  
 <sup>1</sup> im Gegensatz zu einer Variablen entspricht der Wert einer Eigenschaft möglicherweise nicht direkt einem einzelnen Speicher Element. Der Speicher kann aus Gründen der Sicherheit oder der Sicherheit in Teile aufgeteilt werden, oder der Wert kann in verschlüsselter Form gespeichert werden. In diesen Fällen würde die Prozedur die Teile zusammenstellen `Get` oder den gespeicherten Wert entschlüsseln, und die `Set` Prozedur würde den neuen Wert verschlüsseln oder in den enthaltenen Speicher aufteilen. Ein Eigenschafts Wert kann kurzlebig sein, wie z. b. die Tageszeit. in diesem Fall `Get` würde die Prozedur Sie bei jedem Zugriff auf die Eigenschaft bei der Ausführung berechnen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)
- [Vorgehensweise: Erstellen einer Eigenschaft](./how-to-create-a-property.md)
- [Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Vorgehensweise: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)
- [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)
- [Vorgehensweise: Ablegen eines Werts in eine Eigenschaft](./how-to-put-a-value-in-a-property.md)
- [Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
