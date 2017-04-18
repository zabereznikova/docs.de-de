---
title: "Lokaler Typrückschluss (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- local type inference
- vb.TypeInfer
dev_langs:
- VB
helpviewer_keywords:
- Option Infer statement
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2bb673ce871b8e875f62c373404a849c139ab598
ms.lasthandoff: 03/13/2017

---
# <a name="local-type-inference-visual-basic"></a>Lokaler Typrückschluss (Visual Basic)
Visual Basic-Compiler verwendet *Typrückschluss* bestimmt die Datentypen von lokalen Variablen deklariert werden, ohne eine `As` Klausel. Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab. Dadurch können Sie Variablen zu deklarieren, ohne explizit einen Typ anzugeben, wie im folgenden Beispiel gezeigt. Ergebnis der Deklarationen sind beide `num1` und `num2` sind stark typisiert als ganze Zahlen.  
  
 [!code-vb[VbVbalrTypeInference&#1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
  
> [!NOTE]
>  Wenn Sie nicht möchten `num2` im vorherigen Beispiel als typisiert wird ein `Integer`, Sie können einen anderen Typ angeben, indem Sie mit einer Deklaration wie `Dim num3 As Object = 3` oder `Dim num4 As Double = 3`.  
  
 Lokaler Typrückschluss gilt auf Prozedurebene. Er kann nicht zum Deklarieren von Variablen auf Modulebene (innerhalb einer Klasse, Struktur, Modul oder Schnittstelle jedoch nicht innerhalb einer Prozedur oder eines Blocks) verwendet werden. Wenn `num2` im vorherigen Beispiel wurden ein Feld einer Klasse anstelle einer lokalen Variablen in einer Prozedur, die Deklaration würde einen Fehler mit `Option Strict` , und klassifizieren `num2` als ein `Object` mit `Option Strict` deaktiviert. Auf ähnliche Weise lokaler Typrückschluss gilt nicht für Verfahren auf Variablen, die als `Static`.  
  
## <a name="type-inference-vs-late-binding"></a>Typrückschluss und Späte Bindung  
 Code, der Typrückschluss verwendet ähnelt Code, der auf die späte Bindung beruht. Typrückschluss Typen jedoch dringend die Variable verlassen, als `Object`. Der Compiler verwendet eine Variable Initialisierer bestimmt den Typ der Variablen zum Zeitpunkt der Kompilierung zu früh gebundenen Code zu erzeugen. Im vorherigen Beispiel `num2`, z. B. `num1`, als typisiert ist, eine `Integer`.  
  
 Das Verhalten früh gebundener Variablen unterscheidet sich von dem spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist. Frühes der Typ den Compiler Probleme vor der Ausführung erkennen, Speicher genau zuordnen und weitere Optimierungen durchführen. Frühes Binden ermöglicht auch die Visual Basic-IDE (IDE), um IntelliSense-Hilfe zu den Mitgliedern eines Objekts bereitzustellen. Frühe Bindung ist auch für Leistung bevorzugt. Dies ist, da alle in einer spät gebundenen Variable gespeicherte Daten als Typ eingebunden sein müssen `Object`, und Zugreifen auf Member des Typs zur Laufzeit des Programms langsamer macht.  
  
## <a name="examples"></a>Beispiele  
 Typrückschluss erfolgt, wenn eine lokale Variable, ohne deklariert wird eine `As` -Klausel und initialisiert. Der Compiler verwendet den Typ des zugewiesenen Anfangswerts als Typ der Variablen. Die folgenden Zeilen des Codes deklariert beispielsweise eine Variable vom Typ `String`.  
  
 [!code-vb[VbVbalrTypeInference&#2;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 Der folgende Code zeigt zwei äquivalente Verfahren, um ein Array von ganzen Zahlen zu erstellen.  
  
 [!code-vb[VbVbalrTypeInference&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 Es empfiehlt sich, den Typrückschluss verwenden, um den Typ einer Schleifensteuerungsvariablen zu bestimmen. Im folgenden Code wird der Compiler folgert, die `number` ist ein `Integer` da `someNumbers2` aus dem vorherigen Beispiel wird ein Array von Ganzzahlen.  
  
 [!code-vb[VbVbalrTypeInference&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 Lokaler Typrückschluss verwendet werden kann, `Using` Anweisungen, die den Typ des Ressourcennamens, einrichten, wie im folgende Beispiel veranschaulicht.  
  
 [!code-vb[VbVbalrTypeInference&#7;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 Der Typ einer Variablen kann die Rückgabewerte von Funktionen auch abgeleitet werden, wie im folgende Beispiel veranschaulicht. Beide `pList1` und `pList2` von Prozessen sind, da `Process.GetProcesses` gibt ein Array von Prozessen.  
  
 [!code-vb[VbVbalrTypeInference&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a>Option Infer  
 `Option Infer`können, die Sie angeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist. Aktivieren oder die Option blockieren, geben Sie einen der folgenden Anweisungen am Anfang der Datei ein.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Wenn Sie keinen Wert für angeben `Option Infer` in Ihrem Code der Compilerstandardwert ist `Option Infer On`. Für aktualisierte Projekte aus [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] oder früher, der Compilerstandardwert ist `Option Infer Off`.  
  
 Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.  
  
 Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="restrictions"></a>Beschränkungen  
 Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Er kann nicht verwendet werden, um den Typ der Klassenfelder, Eigenschaften oder Funktionen zu ermitteln.  
  
## <a name="see-also"></a>Siehe auch  
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)   
 [Für jede... Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Für... Next-Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [/ optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
