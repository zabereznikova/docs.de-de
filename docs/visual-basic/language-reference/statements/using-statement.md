---
title: Using-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 6ec0e228b3898f66f27e322b5db2dd7f3bf3d7d6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352758"
---
# <a name="using-statement-visual-basic"></a>Using-Anweisung (Visual Basic)

Deklariert den Anfang eines `Using` Blocks und ruft optional die Systemressourcen ab, die der Block steuert.

## <a name="syntax"></a>Syntax

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>-Komponenten

|Begriff|Definition|  
|---|---|  
|`resourcelist`|Erforderlich, wenn Sie keine `resourceexpression`bereitstellen. Eine Liste mit einer oder mehreren Systemressourcen, die von dieser `Using` blockiert werden, durch Kommas getrennt.|  
|`resourceexpression`|Erforderlich, wenn Sie keine `resourcelist`bereitstellen. Verweis Variable oder-Ausdruck, die auf eine System Ressource verweist, die von diesem `Using` Block gesteuert werden soll.|  
|`statements`|Optional. Ein Block von-Anweisungen, die der `Using`-Block ausführt.|  
|`End Using`|Erforderlich Beendet die Definition des `Using` Blocks und gibt alle von ihm kontrollierten Ressourcen frei.|  

 Jede Ressource im `resourcelist` Teil hat die folgende Syntax und die folgenden Teile:

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 \- oder -

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>resourceList-Teile

|Begriff|Definition|  
|---|---|  
|`resourcename`|Erforderlich Verweis Variable, die auf eine System Ressource verweist, die von der `Using` blockiert wird.|  
|`New`|Erforderlich, wenn die `Using`-Anweisung die Ressource abruft. Wenn Sie die Ressource bereits abgerufen haben, verwenden Sie die zweite Syntax Alternative.|  
|`resourcetype`|Erforderlich Die Klasse der Ressource. Die-Klasse muss die <xref:System.IDisposable>-Schnittstelle implementieren.|  
|`arglist`|Optional. Liste von Argumenten, die Sie an den Konstruktor übergeben, um eine Instanz von `resourcetype`zu erstellen. Siehe [Parameter Liste](parameter-list.md).|  
|`resourceexpression`|Erforderlich Eine Variable oder ein Ausdruck, der auf eine System Ressource verweist, die die Anforderungen von `resourcetype`erfüllt. Wenn Sie die zweite Syntax Alternative verwenden, müssen Sie die Ressource abrufen, bevor Sie die Steuerung an die `Using`-Anweisung übergeben.|  
  
## <a name="remarks"></a>Hinweise

 Manchmal erfordert Ihr Code eine nicht verwaltete Ressource, z. b. ein Datei Handle, einen COM-Wrapper oder eine SQL-Verbindung. Ein `Using` Block gewährleistet, dass mindestens eine solche Ressource freigegeben wird, wenn der Code damit fertig ist. Dies macht Sie für anderen Code verfügbar.

 Verwaltete Ressourcen werden vom .NET Framework Garbage Collector (GC) verworfen, ohne dass zusätzliche Codierungen vorhanden sind. Sie benötigen keinen `Using`-Block für verwaltete Ressourcen. Sie können jedoch weiterhin einen `Using`-Block verwenden, um die Freigabe einer verwalteten Ressource zu erzwingen, anstatt auf die Garbage Collector zu warten.

 Ein `Using`-Block besteht aus drei Teilen: Erwerb, Verwendung und Entsorgung.

- Der *Erwerb* bedeutet, dass eine Variable erstellt und initialisiert wird, um auf die System Ressource zu verweisen. Mit der `Using`-Anweisung können Sie eine oder mehrere Ressourcen abrufen, oder Sie können genau eine Ressource abrufen, bevor Sie den Block eingeben und für die `Using`-Anweisung bereitstellen. Wenn Sie `resourceexpression`bereitstellen, müssen Sie die Ressource abrufen, bevor Sie die Steuerung an die `Using`-Anweisung übergeben.

- *Verwendung* bedeutet, dass auf die Ressourcen zugegriffen und Aktionen mit Ihnen durchgeführt werden. Die Anweisungen zwischen `Using` und `End Using` repräsentieren die Verwendung der Ressourcen.

- Die *Beseitigung* bedeutet, dass die <xref:System.IDisposable.Dispose%2A>-Methode für das-Objekt in `resourcename`aufgerufen wird. Dies ermöglicht es dem-Objekt, seine Ressourcen ordnungsgemäß zu beenden. Die `End Using`-Anweisung gibt die Ressourcen unter dem Steuerelement des `Using` Blocks frei.

## <a name="behavior"></a>Verhalten

 Ein `Using`-Block verhält sich wie ein `Try`...`Finally` Konstruktion, in der der `Try` Block die Ressourcen verwendet und der `Finally` Block diese freigibt. Aus diesem Grund wird durch den `Using` Block die Beseitigung der Ressourcen garantiert, unabhängig davon, wie Sie den Block beenden. Dies gilt auch im Fall einer nicht behandelten Ausnahme, mit Ausnahme eines <xref:System.StackOverflowException>.

 Der Gültigkeitsbereich jeder Ressourcenvariablen, die durch die `Using`-Anweisung abgerufen wird, ist auf den `Using`-Block beschränkt.

 Wenn Sie in der `Using`-Anweisung mehr als eine System Ressource angeben, ist der Effekt identisch mit der geschachtelten `Using` Blöcke innerhalb einer anderen.

 Wenn `resourcename` `Nothing`ist, wird kein <xref:System.IDisposable.Dispose%2A> aufgerufen, und es wird keine Ausnahme ausgelöst.

## <a name="structured-exception-handling-within-a-using-block"></a>Strukturierte Ausnahmebehandlung innerhalb eines using-Blocks

 Wenn Sie eine Ausnahme behandeln müssen, die möglicherweise im `Using`-Block auftritt, können Sie eine komplette `Try`...`Finally`-Konstruktion hinzufügen. Wenn Sie den Fall behandeln müssen, in dem die `Using`-Anweisung beim Abrufen einer Ressource nicht erfolgreich ist, können Sie überprüfen, ob `resourcename` `Nothing`ist.

## <a name="structured-exception-handling-instead-of-a-using-block"></a>Strukturierte Ausnahmebehandlung anstelle eines using-Blocks

 Wenn Sie eine präzisere Kontrolle über den Erwerb der Ressourcen benötigen oder zusätzlichen Code im `Finally`-Block benötigen, können Sie den `Using`-Block als `Try`...`Finally` Konstruktion umschreiben. Im folgenden Beispiel werden Skeleton `Try` und `Using` Konstruktionen veranschaulicht, die im Erwerb und der Entsorgung von `resource`äquivalent sind.

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
> Der Code innerhalb des `Using` Blocks sollte das Objekt in `resourcename` nicht einer anderen Variablen zuweisen. Wenn Sie den `Using`-Block beenden, wird die Ressource verworfen, und die andere Variable kann nicht auf die Ressource zugreifen, auf die Sie verweist.

## <a name="example"></a>Beispiel

 Im folgenden Beispiel wird eine Datei mit dem Namen Log. txt erstellt, und es werden zwei Textzeilen in die Datei geschrieben. Das Beispiel liest auch dieselbe Datei und zeigt die Textzeilen an:

 Da die Klassen <xref:System.IO.TextWriter> und <xref:System.IO.TextReader> die <xref:System.IDisposable>-Schnittstelle implementieren, kann der Code `Using`-Anweisungen verwenden, um sicherzustellen, dass die Datei nach den Schreib-und Lesevorgängen ordnungsgemäß geschlossen wird.

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>Siehe auch

- <xref:System.IDisposable>
- [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md)
- [Gewusst wie: Freigeben einer Systemressource](../../programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)
