---
title: Using-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 36
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ed9cc0d04c89eac1fe342a0924dd89bb1e258a11
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
|`resourcelist`|Erforderlich, wenn Sie keine angeben `resourceexpression`. Liste der Systemressourcen für eine oder mehrere, die von diesem `Using` blockieren, Steuerelemente, die durch Kommas getrennt.|  
|`resourceexpression`|Erforderlich, wenn Sie keine angeben `resourcelist`. Verweisvariable oder einen Ausdruck verweist auf eine Systemressource, die von diesem gesteuert werden `Using` Block.|  
|`statements`|Dies ist optional. Block von Anweisungen, die die `Using` -Block ausgeführt.|  
|`End Using`|Erforderlich. Beendet die Definition des der `Using` Block und verwirft alle Ressourcen an, die er steuert.|  
  
 Jede Ressource in der `resourcelist` Teil hat die folgende Syntax und Bestandteile:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 - oder -   
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>ResourceList-Teile  
  
|Begriff|Definition|  
|---|---|  
|`resourcename`|Erforderlich. Verweisvariable, der auf eine Systemressource verweist, die die `Using` Steuerelemente zu blockieren.|  
|`New`|Erforderlich, wenn die `Using` -Anweisung ruft die Ressource ab. Wenn Sie die Ressource bereits abgerufen haben, verwenden Sie die zweite Syntax Alternative.|  
|`resourcetype`|Erforderlich. Die Klasse der Ressource. Implementieren Sie die Klasse muss die <xref:System.IDisposable> Schnittstelle.|  
|`arglist`|Dies ist optional. Liste von Argumenten an den Konstruktor zum Erstellen einer Instanz von übergeben `resourcetype`. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Erforderlich. Variable oder ein Ausdruck verweist auf eine Systemressource, erfüllen die Anforderungen des `resourcetype`. Wenn Sie in der zweiten Alternative Syntax verwenden, müssen Sie die Ressource abrufen, bevor Sie übergeben der Steuerung an die `Using` Anweisung.|  
  
## <a name="remarks"></a>Hinweise  
 Mitunter muss Ihren Code eine nicht verwaltete Ressource, z. B. ein Dateihandle, ein COM-Wrapper oder eine SQL-Verbindung. Ein `Using` Block gewährleistet die Freigabe dieser Ressourcen aus, wenn mit diesen Code abgeschlossen ist. Dadurch sind sie von anderem Code zu verwenden.  
  
 Verwaltete Ressourcen werden der von der .NET Framework-Garbage Collector (GC) freigegeben, ohne zusätzliche Codierung ihrerseits. Sie müssen keine `Using` Block für die verwalteten Ressourcen. Allerdings können Sie weiterhin verwenden eine `Using` Block, um die Freigabe einer verwalteten Ressource nicht erst, wenn für den Garbage Collector zu erzwingen.  
  
 Ein `Using` Block besteht aus drei Teilen: Abruf, Verwendung und Freigabe.  
  
-   *Erhalt* bedeutet, dass eine Variable erstellen und initialisieren es auf der Systemressource verweist. Die `Using` Anweisung kann eine oder mehrere Ressourcen erwerben oder können Sie genau eine Ressource vor dem Wechsel in des Blocks abzurufen und sie zum Bereitstellen der `Using` Anweisung. Wenn Sie angeben `resourceexpression`, Sie müssen die Ressource abrufen, bevor Sie übergeben der Steuerung an die `Using` Anweisung.  
  
-   *Verwendung* bedeutet, dass Zugriff auf die Ressourcen und Aktionen ausführen. Die Anweisungen zwischen `Using` und `End Using` die Nutzung der Ressourcen darstellen.  
  
-   *Beseitigung* aufrufen bedeutet, dass die <xref:System.IDisposable.Dispose%2A> Methode für das Objekt in `resourcename`. Dadurch wird das Objekt seine Ressourcen sauber beendet. Die `End Using` Anweisung verwirft die Ressourcen unter der `Using` des TextBlock-Steuerelement.  
  
## <a name="behavior"></a>Verhalten  
 Ein `Using` Block verhält sich wie ein `Try`... `Finally` Konstruktion, in dem die `Try` Block verwendet wird, die Ressourcen und die `Finally` Block freigegeben werden. Aus diesem Grund die `Using` Block wird sichergestellt, Freigabe von Ressourcen, unabhängig davon, wie Sie den Block zu beenden. Dies gilt sogar im Fall einer nicht behandelten Ausnahme, mit Ausnahme von einer <xref:System.StackOverflowException>.  
  
 Rahmen jeder Ressourcenvariablen durch die `Using` Anweisung ist auf die `Using` Block.  
  
 Bei Angabe von mehr als eine Systemressource, die in der `Using` -Anweisung, die Auswirkung ist identisch, als ob Sie geschachtelte `Using` ineinander blockiert.  
  
 Wenn `resourcename` ist `Nothing`, ohne Aufruf <xref:System.IDisposable.Dispose%2A> erfolgt, und es wird keine Ausnahme ausgelöst.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Innerhalb eines Blocks verwenden die strukturierte Ausnahmebehandlung  
 Wenn Sie eine Ausnahme zu behandeln, die innerhalb von auftreten müssen die `Using` blockieren, können Sie eine vollständige hinzufügen `Try`... `Finally` -Konstruktion hinzufügen. Wenn Sie die Groß-/Kleinschreibung behandeln müssen, in dem die `Using` Anweisung ist nicht beim Abrufen einer Ressourcenpools erfolgreich, Sie können testen, um festzustellen, wenn `resourcename` ist `Nothing`.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Strukturierte Ausnahmebehandlung anstelle eines Blocks verwenden  
 Wenn Sie eine präzisere Steuerung der Übernahme der Ressourcen, benötigen Sie zusätzlichen Code in der `Finally` blockieren, können Sie Umschreiben der `Using` als blockiert eine `Try`... `Finally` Konstruktion. Das folgende Beispiel zeigt Skeleton `Try` und `Using` Konstruktionen, die in den Erhalt und die Beseitigung von entsprechen `resource`.  
  
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
>  Der Code innerhalb der `Using` Block sollten nicht das Objekt im zuweisen `resourcename` einer anderen Variablen. Wenn Sie beenden die `Using` blockieren, die Ressource freigegeben wird, und die andere Variable kann nicht auf den er zeigt Ressource zuzugreifen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine Datei mit dem Namen log.txt und zwei Textzeilen in die Datei schreibt. Im Beispiel wird auch liest diese Datei und zeigt die Textzeilen.  
  
 Da die <xref:System.IO.TextWriter> und <xref:System.IO.TextReader> Klassen implementieren die <xref:System.IDisposable> -Schnittstelle, die den Code verwenden kann `Using` Anweisungen, um sicherzustellen, dass die Datei ordnungsgemäß werden, nach dem Schreiben geschlossen und Lesevorgänge.  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.IDisposable>  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Gewusst wie: Freigeben einer Systemressource](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
