---
title: Using-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 1cf0772bf4e9a77474849c59454617261475fa76
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966085"
---
# <a name="using-statement-visual-basic"></a>Using-Anweisung (Visual Basic)
Deklariert den Beginn einer `Using` blockieren und ruft optional die Systemressourcen, die steuert, der Block ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`resourcelist`|Erforderlich, wenn Sie keinen angeben `resourceexpression`. Liste der Systemressourcen für eine oder mehrere, das von diesem `Using` Steuerelemente, die durch Kommas getrennt zu blockieren.|  
|`resourceexpression`|Erforderlich, wenn Sie keinen angeben `resourcelist`. Reference-Variable oder einen Ausdruck verweist auf eine Systemressource, die von diesem gesteuert werden `Using` Block.|  
|`statements`|Dies ist optional. Block von Anweisungen, die die `Using` -Block ausgeführt.|  
|`End Using`|Erforderlich. Beendet die Definition der `Using` Block frei und verwirft alle Ressourcen, die es steuert.|  
  
 Jede Ressource in der `resourcelist` Teil weist die folgende Syntax und Bestandteile:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 - oder -   
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>ResourceList Teilen  
  
|Begriff|Definition|  
|---|---|  
|`resourcename`|Erforderlich. Reference-Variable, die auf eine Systemressource verweist, die die `Using` Steuerelemente zu blockieren.|  
|`New`|Erforderlich, wenn die `Using` -Anweisung ruft die Ressource ab. Wenn Sie die Ressource bereits abgerufen haben, verwenden Sie die zweite Syntax Alternative.|  
|`resourcetype`|Erforderlich. Die Klasse der Ressource. Implementieren Sie die Klasse muss die <xref:System.IDisposable> Schnittstelle.|  
|`arglist`|Dies ist optional. Liste von Argumenten, die an den Konstruktor zum Erstellen einer Instanz von übergeben `resourcetype`. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Erforderlich. Variable oder einen Ausdruck verweist auf eine Systemressource, erfüllen die Anforderungen der `resourcetype`. Wenn Sie die Alternative der zweite Syntax verwenden, müssen Sie die Ressource abrufen, bevor Sie übergeben der Steuerung an die `Using` Anweisung.|  
  
## <a name="remarks"></a>Hinweise  
 Manchmal muss Ihr Code eine nicht verwaltete Ressource, z. B. ein Dateihandle, ein COM-Wrapper oder eine SQL-Verbindung. Ein `Using` Block garantiert das Verwerfen von ein oder mehrere solcher Ressourcen aus, wenn Ihr Code mit diesen abgeschlossen ist. Dadurch werden sie von anderem Code zu verwenden.  
  
 Verwaltete Ressourcen sind von durch den .NET Framework-Garbage Collector (GC) freigegeben, ohne dass zusätzliche Programmieren ihrerseits. Sie müssen keine `Using` Block für die verwalteten Ressourcen. Allerdings können Sie weiterhin verwenden eine `Using` Block, um die Freigabe einer verwalteten Ressource anstatt abzuwarten, bis der Garbage Collector zu erzwingen.  
  
 Ein `Using` Block besteht aus drei Teilen: Abruf, Verwendung und Freigabe.  
  
-   *Übernahme* bedeutet, dass eine Variable erstellen und initialisieren es auf die Systemressource verweist. Die `Using` Anweisung kann eine oder mehrere Ressourcen abrufen, oder Sie genau eine Ressource vor dem Eingeben des Blocks abrufen können, und stellen sie die `Using` Anweisung. Wenn Sie angeben, `resourceexpression`, Sie müssen die Ressource abrufen, bevor Sie übergeben der Steuerung an die `Using` Anweisung.  
  
-   *Nutzung* bedeutet, dass Zugriff auf die Ressourcen und Aktionen mit der sie ausgeführt werden. Die Anweisungen zwischen `Using` und `End Using` die Nutzung von Ressourcen darstellen.  
  
-   *Beseitigung* aufrufen bedeutet, dass die <xref:System.IDisposable.Dispose%2A> Methode für das Objekt in `resourcename`. Dadurch wird das Objekt seine Ressourcen sauber beendet. Die `End Using` Anweisung löscht Ressourcen in der `Using` des TextBlock-Steuerelement.  
  
## <a name="behavior"></a>Verhalten  
 Ein `Using` Block verhält sich wie ein `Try`... `Finally` Konstruktion, in dem die `Try` Block verwendet die Ressourcen und die `Finally` Block freigegeben werden. Aus diesem Grund die `Using` Block gewährleistet die Freigabe von Ressourcen, unabhängig davon, wie Sie den Block zu beenden. Dies gilt auch bei einem Ausnahmefehler, mit Ausnahme von einer <xref:System.StackOverflowException>.  
  
 Den Rahmen jeder Ressourcenvariablen durch die `Using` Anweisung ist auf die `Using` Block.  
  
 Bei Angabe von mehr als eine Systemressource, die in der `Using` -Anweisung, die Auswirkung ist identisch, als ob Sie verschachtelte `Using` eine innerhalb einer anderen werden blockiert.  
  
 Wenn `resourcename` ist `Nothing`, kein Aufruf von <xref:System.IDisposable.Dispose%2A> vorgenommen wird, und es wird keine Ausnahme ausgelöst.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Strukturierte Ausnahmebehandlung innerhalb eines Blocks verwenden  
 Wenn Sie eine Ausnahme zu behandeln, die in auftreten müssen die `Using` blockieren, können Sie eine vollständige hinzufügen `Try`... `Finally` -Konstruktion hinzufügen. Wenn Sie den Fall behandeln müssen, in denen die `Using` Anweisung ist nicht erfolgreich eine Ressource abgerufen, können Sie testen, finden Sie unter `resourcename` ist `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Strukturierte Ausnahmebehandlung anstelle eines Blocks verwenden  
 Wenn Sie eine präzisere Kontrolle über den Erwerb von Ressourcen, oder Sie zusätzlichen Code in benötigen der `Finally` Block kann neu geschrieben werden die `Using` -Blocks als eine `Try`... `Finally` Konstruktion. Das folgende Beispiel zeigt Gerüst `Try` und `Using` Konstruktionen, die in den Erwerb und die Freigabe entsprechen `resource`.  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  Der Code in die `Using` Block sollten nicht das Objekt im zuweisen `resourcename` einer anderen Variablen. Wenn Sie beenden die `Using` blockieren, die Ressource freigegeben wird, und die andere Variable kann nicht auf die Ressource, die auf den er zeigt zugreifen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Datei mit dem Namen "log.txt" und zwei Textzeilen in die Datei schreibt. Im Beispiel wird auch der gleichen Datei liest und die Zeilen des Texts angezeigt.  
  
 Da die <xref:System.IO.TextWriter> und <xref:System.IO.TextReader> -Klassen implementieren die <xref:System.IDisposable> -Schnittstelle, die den Code verwenden kann `Using` Anweisungen, um sicherzustellen, dass die Datei korrekt wird, nach dem Schreiben geschlossen und Lesevorgänge.  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.IDisposable>
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Vorgehensweise: Freigeben einer Systemressource](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
