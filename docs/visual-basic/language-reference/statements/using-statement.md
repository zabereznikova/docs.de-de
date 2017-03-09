---
title: "Using Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.using"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "resource disposal"
  - "Try...Catch...Finally statements, equivalent to Using statement"
  - "resources [Visual Basic], disposing"
  - "Using statement"
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
caps.latest.revision: 36
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 36
---
# Using Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Deklariert den Beginn eines `Using`\-Blocks und ruft optional die Systemressourcen ab, die von dem Block gesteuert werden.  
  
## Syntax  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`resourcelist`|Erforderlich, wenn Sie `resourceexpression` nicht angeben.  Liste mit einer oder mehreren Systemressourcen die Steuerelemente `Using` dieses Blocks, durch Trennzeichen getrennt.|  
|`resourceexpression`|Erforderlich, wenn Sie `resourcelist` nicht angeben.  Verweisvariable oder \-ausdruck, die bzw. der auf eine Systemressource verweist, die von diesem `Using`\-Block gesteuert werden soll.|  
|`statements`|Dies ist optional.  Block von Anweisungen, die vom `Using`\-Block ausgeführt werden.|  
|`End Using`|Erforderlich.  Beendet die Definition des `Using`\-Blocks und gibt alle Ressourcen frei, die von dem Block gesteuert werden.|  
  
 Jede Ressource im `resourcelist`\-Teil weist die folgende Syntax und die folgenden Bestandteile auf:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 \- oder \-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## Bestandteile von "resourcelist"  
  
|||  
|-|-|  
|Begriff|Definition|  
|`resourcename`|Erforderlich.  Verweisvariable, die auf eine vom `Using`\-Block gesteuerte Systemressource verweist.|  
|`New`|Erforderlich, wenn die `Using`\-Anweisung die Ressource abruft.  Wenn Sie die Ressource bereits abgerufen haben, verwenden Sie die zweite Alternative der Syntax.|  
|`resourcetype`|Erforderlich.  Die Klasse der Ressource.  Die Klasse muss die <xref:System.IDisposable>\-Schnittstelle implementieren.|  
|`arglist`|Dies ist optional.  Liste der Argumente, die Sie an den Konstruktor übergeben, um eine Instanz von `resourcetype` zu erstellen.  Siehe [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`resourceexpression`|Erforderlich.  Variable oder Ausdruck, der bzw. die auf eine Systemressource verweist, die die Anforderungen von `resourcetype` erfüllt.  Wenn Sie die zweite Alternative der Syntax verwenden, müssen Sie die Ressource abrufen, bevor die Steuerung an die `Using`\-Anweisung übergeben wird.|  
  
## Hinweise  
 Zuweilen erfordert Code eine nicht verwaltete Ressource, z. B. ein Dateihandle, einen COM\-Wrapper oder eine SQL\-Verbindung.  Mit einem `Using`\-Block wird die Freigabe einer oder mehrerer dieser Ressourcen nach ihrer Behandlung durch den Code sichergestellt.  Hierdurch werden sie für die Verwendung durch anderen Code verfügbar.  
  
 Verwaltete Ressourcen werden vom Garbage Collector \(GC\) von .NET Framework freigegeben. Sie müssen hierfür keinen zusätzlichen Code schreiben.  Für verwaltete Ressourcen ist kein `Using`\-Block erforderlich.  Dennoch können Sie einen `Using`\-Block verwenden, um die Beseitigung einer verwalteten Ressource zu erzwingen anstatt auf den Garbage Collector zu warten.  
  
 Ein `Using`\-Block besteht aus drei Teilen: Abruf, Verwendung und Freigabe.  
  
-   *Abruf* bedeutet, dass eine Variable erstellt und für den Verweis auf die Systemressource initialisiert wird.  Die `Using`\-Anweisung kann eine oder mehrere Ressourcen abrufen. Sie können auch genau eine Ressource abrufen, bevor der Block ausgeführt wird, und sie für die `Using`\-Anweisung bereitstellen.  Wenn Sie `resourceexpression` angeben, müssen Sie die Ressource abrufen, bevor die Steuerung an die `Using`\-Anweisung übergeben wird.  
  
-   *Verwendung* bedeutet, dass auf die Ressourcen zugegriffen wird und Aktionen mit ihnen ausgeführt werden.  Die Anweisungen zwischen `Using` und `End Using` stellen die Verwendung der Ressourcen dar.  
  
-   *Freigabe* bedeutet, dass für das Objekt in `resourcename` die <xref:System.IDisposable.Dispose%2A>\-Methode aufgerufen wird.  Dies ermöglicht dem Objekt, seine Ressourcen sauber zu beenden.  Mit der `End Using`\-Anweisung werden die vom `Using`\-Block gesteuerten Ressourcen freigegeben.  
  
## Verhalten  
 Das Verhalten eines `Using`\-Blocks entspricht dem Verhalten einer `Try`...`Finally`\-Konstruktion, in deren `Try`\-Block die Ressourcen verwendet und in deren `Finally`\-Block die Ressourcen freigegeben werden.  Aus diesem Grund wird die Freigabe der Ressourcen durch den `Using`\-Block sichergestellt, unabhängig davon, wie Sie den Block beenden.  Dies gilt sogar im Fall einer nicht behandelten Ausnahme, allerdings nicht bei einer <xref:System.StackOverflowException>.  
  
 Der Gültigkeitsbereich jeder von der `Using`\-Anweisung abgerufenen Ressourcenvariablen ist auf den `Using`\-Block beschränkt.  
  
 Wenn Sie in der `Using`\-Anweisung mehrere Systemressourcen angeben, hat dies dieselbe Auswirkung wie das Schachteln mehrerer `Using`\-Blocks.  
  
 Wenn `resourcename``Nothing` ist, wird kein Aufruf <xref:System.IDisposable.Dispose%2A> gemacht, und es wird keine Ausnahme ausgelöst.  
  
## Strukturierte Ausnahmebehandlung in einem Using\-Block  
 Wenn Sie eine Ausnahme behandeln müssen, die möglicherweise in einem `Using`\-Block auftritt, können Sie diesem eine vollständige `Try`...`Finally`\-Konstruktion hinzufügen.  Wenn Sie den Fall behandeln müssen, dass eine Ressource von einer `Using`\-Anweisung nicht erfolgreich abgerufen wird, können Sie überprüfen, ob `resourcename` `Nothing` ist.  
  
## Strukturierte Ausnahmebehandlung anstelle eines Using\-Blocks  
 Wenn Sie den Abruf der Ressourcen genauer steuern müssen oder wenn im `Finally`\-Block zusätzlicher Code erforderlich ist, können Sie den `Using`\-Block in eine `Try`...`Finally`\-Konstruktion ändern.  Im folgenden Beispiel werden die Skelette einer `Try`\-Konstruktion und einer `Using`\-Konstruktion veranschaulicht, die dem Abruf und der Freigabe von `resource` entsprechen.  
  
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
>  Der Code im `Using`\-Block darf das Objekt in `resourcename` keiner anderen Ressource zuweisen.  Beim Beenden des `Using`\-Blocks wird die Ressource freigegeben, und die andere Variable kann nicht auf die Ressource zugreifen, auf die sie zeigt.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Datei mit dem Namen log.txt, und schreibt zwei Textzeilen zur Datei.  Außerdem liest dass dieselbe Datei und zeigt die Textzeilen an.  
  
 Da die <xref:System.IO.TextWriter> und <xref:System.IO.TextReader>\-Klassen die <xref:System.IDisposable>\-Schnittstelle implementieren, kann der Code `Using`\-Anweisungen verwenden, um sicherzustellen, dass die Datei ordnungsgemäß nach dem geschriebene und die Lesevorgänge geschlossen wird.  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/using-statement_1.vb)]  
  
## Siehe auch  
 <xref:System.IDisposable>   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [How to: Dispose of a System Resource](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)