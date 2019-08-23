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
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957544"
---
# <a name="using-statement-visual-basic"></a>Using-Anweisung (Visual Basic)
Deklariert den Anfang eines `Using` -Blocks und ruft optional die Systemressourcen ab, die der-Block steuert.  
  
## <a name="syntax"></a>Syntax  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`resourcelist`|Erforderlich, wenn Sie nicht angeben `resourceexpression`. Liste von mindestens einer System Ressource, die dieser `Using` Block steuert, getrennt durch Kommas.|  
|`resourceexpression`|Erforderlich, wenn Sie nicht angeben `resourcelist`. Verweis Variable oder-Ausdruck, die auf eine System Ressource verweist, die `Using` von diesem Block gesteuert werden soll.|  
|`statements`|Optional. Block von-Anweisungen, `Using` die der-Block ausführt.|  
|`End Using`|Erforderlich. Beendet die Definition des `Using` Blocks und gibt alle von ihm kontrollierten Ressourcen frei.|  
  
 Jede Ressource im `resourcelist` Teil hat die folgende Syntax und die folgenden Teile:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 -oder-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>resourceList-Teile  
  
|Begriff|Definition|  
|---|---|  
|`resourcename`|Erforderlich. Verweis Variable, die auf eine System Ressource verweist, `Using` die der Block steuert.|  
|`New`|Erforderlich, wenn `Using` die-Anweisung die Ressource abruft. Wenn Sie die Ressource bereits abgerufen haben, verwenden Sie die zweite Syntax Alternative.|  
|`resourcetype`|Erforderlich. Die Klasse der Ressource. Die-Klasse muss die <xref:System.IDisposable> -Schnittstelle implementieren.|  
|`arglist`|Optional. Liste von Argumenten, die Sie an den Konstruktor übergeben, um eine Instanz `resourcetype`von zu erstellen. Siehe [Parameter Liste](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Erforderlich. Eine Variable oder ein Ausdruck, der auf eine System Ressource verweist `resourcetype`, die die Anforderungen von erfüllt. Wenn Sie die zweite Syntax Alternative verwenden, müssen Sie die Ressource abrufen, bevor Sie die Steuerung `Using` an die-Anweisung übergeben.|  
  
## <a name="remarks"></a>Hinweise  
 Manchmal erfordert Ihr Code eine nicht verwaltete Ressource, z. b. ein Datei Handle, einen COM-Wrapper oder eine SQL-Verbindung. Ein `Using` -Block gewährleistet, dass mindestens eine solche Ressource freigegeben wird, wenn der Code damit fertig ist. Dies macht Sie für anderen Code verfügbar.  
  
 Verwaltete Ressourcen werden vom .NET Framework Garbage Collector (GC) verworfen, ohne dass zusätzliche Codierungen vorhanden sind. Sie benötigen `Using` keinen Block für verwaltete Ressourcen. Sie können jedoch weiterhin einen `Using` -Block verwenden, um die Freigabe einer verwalteten Ressource zu erzwingen, anstatt auf die Garbage Collector zu warten.  
  
 Ein `Using` -Block besteht aus drei Teilen: Erwerb, Verwendung und Entsorgung.  
  
- Der *Erwerb* bedeutet, dass eine Variable erstellt und initialisiert wird, um auf die System Ressource zu verweisen. Die `Using` -Anweisung kann eine oder mehrere Ressourcen abrufen, oder Sie können genau eine Ressource abrufen, bevor Sie den Block eingeben und an `Using` die-Anweisung übergeben. Wenn Sie angeben `resourceexpression`, müssen Sie die Ressource abrufen, bevor Sie die Steuerung `Using` an die-Anweisung übergeben.  
  
- *Verwendung* bedeutet, dass auf die Ressourcen zugegriffen und Aktionen mit Ihnen durchgeführt werden. Die-Anweisungen `Using` zwischen `End Using` und stellen die Verwendung der Ressourcen dar.  
  
- Die *Beseitigung* bedeutet, <xref:System.IDisposable.Dispose%2A> dass die-Methode für `resourcename`das Objekt in aufgerufen wird. Dies ermöglicht es dem-Objekt, seine Ressourcen ordnungsgemäß zu beenden. Die `End Using` -Anweisung gibt die Ressourcen `Using` des Block-Steuer Elements frei.  
  
## <a name="behavior"></a>Verhalten  
 Ein `Using` -Block verhält sich `Try`wie ein... Konstruktion, bei der `Try` der-Block die Ressourcen verwendet `Finally` und der Block diese freigibt. `Finally` Aus diesem Grund gewährleistet `Using` der-Block die Beseitigung der Ressourcen, unabhängig davon, wie Sie den Block beenden. Dies gilt auch im Fall einer nicht behandelten Ausnahme, mit Ausnahme <xref:System.StackOverflowException>von.  
  
 Der Gültigkeitsbereich jeder von der `Using` -Anweisung abgerufenen Ressourcenvariablen ist auf den `Using` -Block beschränkt.  
  
 Wenn Sie in der `Using` -Anweisung mehr als eine System Ressource angeben, entspricht der Effekt dem, wenn Sie Blöcke innerhalb einer anderen geschachtelt `Using` haben.  
  
 Wenn `resourcename` <xref:System.IDisposable.Dispose%2A> ist `Nothing`, wird kein-Rückruf durchgeführt, und es wird keine Ausnahme ausgelöst.  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Strukturierte Ausnahmebehandlung innerhalb eines using-Blocks  
 Wenn Sie eine Ausnahme behandeln müssen, die möglicherweise im `Using` -Block auftritt, können Sie eine Complete `Try`... `Finally` die Erstellung. Wenn Sie den Fall behandeln müssen, in dem `Using` die-Anweisung beim Abrufen einer Ressource nicht erfolgreich ist, können Sie überprüfen `resourcename` , `Nothing`ob ist.  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>Strukturierte Ausnahmebehandlung anstelle eines using-Blocks  
 Wenn Sie eine `Finally` `Using` präzisereKontrolleüberdenErwerbderRessourcenbenötigenoderzusätzlichenCodeim-Blockbenötigen,könnenSiedenBlock`Try`als... `Finally` Konstruktion. Im folgenden Beispiel werden Skeleton `Try` und `Using` Konstruktionen veranschaulicht, die im Erwerb und in der Entsorgung `resource`von äquivalent sind.  
  
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
> Der Code innerhalb des `Using` -Blocks sollte das `resourcename` Objekt nicht einer anderen Variablen zuweisen. Wenn Sie den `Using` -Block beenden, wird die Ressource verworfen, und die andere Variable kann nicht auf die Ressource zugreifen, auf die Sie verweist.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Datei mit dem Namen Log. txt erstellt, und es werden zwei Textzeilen in die Datei geschrieben. Im Beispiel wird auch dieselbe Datei gelesen, und die Textzeilen werden angezeigt.  
  
 Da die <xref:System.IO.TextWriter> - <xref:System.IO.TextReader> Klasse und die <xref:System.IDisposable> -Klasse die-Schnittstelle `Using` implementieren, kann der Code-Anweisungen verwenden, um sicherzustellen, dass die Datei nach Schreib-und Lesevorgängen ordnungsgemäß geschlossen  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IDisposable>
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Vorgehensweise: Verwerfen einer System Ressource](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
