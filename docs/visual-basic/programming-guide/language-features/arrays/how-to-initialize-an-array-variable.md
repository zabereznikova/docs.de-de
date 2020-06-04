---
title: 'Vorgehensweise: Initialisieren einer Arrayvariablen'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], initializing
- arrays [Visual Basic], variables
- arrays [Visual Basic], initializing
- arrays [Visual Basic], declaring
ms.assetid: aadd7a60-7ca4-4608-b986-091f19e7fc10
ms.openlocfilehash: 7feaf71fa1c59c24aa751f2b9e28328d47ba357c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413065"
---
# <a name="how-to-initialize-an-array-variable-in-visual-basic"></a>Gewusst wie: Initialisieren einer Arrayvariablen in Visual Basic
Sie initialisieren eine Arrayvariable, in dem Sie ein Arrayliteral in einer `New`-Klausel einfügen und die Anfangswerte des Arrays angeben. Sie können den Typ angeben oder ihn von den Werten im Arrayliteral ableiten lassen. Weitere Informationen dazu, wie der Typ abgeleitet wird, finden Sie unter "Auffüllen eines Arrays mit Anfangswerten" in [Arrays](index.md).  
  
### <a name="to-initialize-an-array-variable-by-using-an-array-literal"></a>So initialisieren Sie eine Arrayvariable mit einem Arrayliteral  
  
- Geben Sie die Elementwerte in der `New`-Klausel oder beim Zuweisen des Arraywerts in geschweiften Klammern (`{}`) an. Im folgenden Beispiel werden mehrere Möglichkeiten veranschaulicht, wie Variablen so deklariert, erstellt und initialisiert werden können, dass sie ein Array mit Elementen vom Typ `Char` enthalten.  
  
     [!code-vb[VbVbalrArrays#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#16)]  
  
     Nach der Ausführung jeder Anweisung hat das erstellte Array die Länge 3, wobei die Elemente von Index 0 bis Index 2 die Anfangswerte enthalten. Wenn Sie sowohl die Obergrenze als auch die Werte angeben, müssen Sie für jedes Element von Index 0 bis zur Obergrenze einen Wert einfügen.  
  
     Beachten Sie, dass Sie keine Indexobergrenze angeben müssen, wenn Elementwerte in einem Arrayliteral bereitgestellt werden. Wenn keine Obergrenze angegeben wird, wird die Größe des Arrays anhand der Anzahl der Werte im Arrayliteral abgeleitet.  
  
### <a name="to-initialize-a-multidimensional-array-variable-by-using-array-literals"></a>So initialisieren Sie eine mehrdimensionale Arrayvariable mit Arrayliteralen  
  
- Schachteln Sie Werte in geschweiften Klammern (`{}`) in geschweiften Klammern. Stellen Sie sicher, dass alle geschachtelten Arrayliterale als Arrays des gleichen Typs und mit derselben Länge abgeleitet werden. Im folgenden Codebeispiel werden mehrere Beispiele für die Initialisierung mehrdimensionaler Arrays veranschaulicht.  
  
     [!code-vb[VbVbalrArrays#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#17)]  
  
- Sie können die Arraygrenzen explizit angeben oder diese Angabe auslassen, sodass der Compiler die Arraygrenzen von den Werten im Arrayliteral ableitet. Wenn Sie sowohl die Obergrenzen als auch die Werte vorgeben, müssen Sie in jeder Dimension für jedes Element von Index 0 bis zur Obergrenze einen Wert angeben. Im folgenden Beispiel werden mehrere Möglichkeiten veranschaulicht, wie Variablen so deklariert, erstellt und initialisiert werden können, dass sie ein zweidimensionales Array mit Elementen vom Typ `Short` enthalten.  
  
     [!code-vb[VbVbalrArrays#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#18)]  
  
     Nach der Ausführung jeder Anweisung enthält das erstellte Array sechs initialisierte Elemente mit den Indizes `(0,0)`, `(0,1)`, `(0,2)`, `(1,0)`, `(1,1)` und `(1,2)`. Jede Arrayposition enthält den Wert `10`.  
  
- Im folgenden Beispiel wird ein mehrdimensionales Array durchlaufen. Fügen Sie den Code in einer Windows-Konsolenanwendung, die in Visual Basic geschrieben wurde, in die `Sub Main()`-Methode ein. Die letzten Kommentare zeigen die Ausgabe an.  
  
     [!code-vb[VbVbalrArrays#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#31)]  
  
### <a name="to-initialize-a-jagged-array-variable-by-using-array-literals"></a>So initialisieren Sie eine verzweigte Arrayvariable mit Arrayliteralen  
  
- Schachteln Sie Objektwerte in geschweiften Klammern (`{}`). Obwohl Sie Array Literale schachteln können, die Arrays mit unterschiedlicher Länge angeben, stellen Sie im Fall eines Jagged Array sicher, dass die geschachtelten Array Literale in Klammern () eingeschlossen werden `()` . Durch die Klammern wird die Auswertung der geschachtelten Arrayliterale erzwungen, und die erhaltenen Arrays werden als Anfangswerte des verzweigten Arrays verwendet. Im folgenden Codebeispiel werden zwei Beispiele für die Initialisierung verzweigter Arrays veranschaulicht.  
  
     [!code-vb[VbVbalrArrays#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#19)]  
  
- Im folgenden Beispiel wird ein verzweigtes Array durchlaufen. Fügen Sie den Code in einer Windows-Konsolenanwendung, die in Visual Basic geschrieben wurde, in die `Sub Main()`-Methode ein.  Die letzten Kommentare im Code zeigen die Ausgabe an.  
  
     [!code-vb[VbVbalrArrays#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrArrays/VB/Class1.vb#32)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Arrays](index.md)
- [Problembehandlung bei Arrays](troubleshooting-arrays.md)
