---
title: "Gewusst wie: Deklarieren, Instanziieren und Verwenden von Delegaten (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Delegaten [C#], Deklarieren und Instanziieren von"
ms.assetid: 61c4895f-f785-48f8-8bfe-db73b411c4ae
caps.latest.revision: 21
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 21
---
# Gewusst wie: Deklarieren, Instanziieren und Verwenden von Delegaten (C#-Programmierhandbuch)
In C\# 1.0 und höher können Delegaten wie im folgenden Beispiel gezeigt deklariert werden.  
  
 [!code-cs[csProgGuideDelegates#13](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#13)]  
  
 [!code-cs[csProgGuideDelegates#14](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#14)]  
  
 C\# 2.0 bietet eine einfachere Möglichkeit zum Schreiben dieser Deklaration, wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[csProgGuideDelegates#32](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#32)]  
  
 In C\# 2.0 und höher kann auch eine anonyme Methode verwendet werden, um einen [Delegaten](../../../csharp/language-reference/keywords/delegate.md) zu deklarieren und initialisieren, wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[csProgGuideDelegates#15](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#15)]  
  
 In C\# 3.0 und höher können Delegaten auch mit einem Lambda\-Ausdruck deklariert und instanziiert werden, wie im folgenden Beispiel gezeigt.  
  
 [!code-cs[csProgGuideDelegates#31](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#31)]  
  
 Weitere Informationen finden Sie unter [Lambda\-Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
 Im folgenden Beispiel wird verdeutlicht, wie Sie einen Delegaten deklarieren, instanziieren und verwenden.  In der `BookDB`\-Klasse ist eine Buchhandlungsdatenbank gekapselt, die eine Buchtiteldatenbank enthält.  Sie stellt eine `ProcessPaperbackBooks`\-Methode zur Verfügung, durch die alle Taschenbücher in der Datenbank gefunden und für jedes Taschenbuch ein Delegat aufgerufen wird.  Der verwendete `delegate`\-Typ hat den Namen `ProcessBookDelegate`.  Die `Test`\-Klasse verwendet diese Klasse, um die Buchtitel und Durchschnittspreise der Taschenbücher auszugeben.  
  
 Die Verwendung von Delegaten beinhaltet eine sinnvolle Trennung der Funktionalitäten von Buchhandlungsdatenbank und Clientcode.  Der Clientcode weiß nicht, wie die Bücher archiviert werden oder wie der Buchhandlungscode Taschenbücher sucht.  Der Buchhandlungscode wiederum weiß nicht, wie ein Taschenbuchtitel weiterverarbeitet wird, nachdem er gefunden wurde.  
  
## Beispiel  
 [!code-cs[csProgGuideDelegates#12](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#12)]  
  
## Robuste Programmierung  
  
-   Deklarieren von Delegaten  
  
     Mit der folgenden Anweisung wird ein neuer Delegattyp deklariert.  
  
     [!code-cs[csProgGuideDelegates#16](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#16)]  
  
     Durch die einzelnen Delegattypen werden Anzahl und Typen von Argumenten sowie Rückgabewerte von Methoden beschrieben, die gekapselt können.  Sobald neue Argumenttypen oder ein neuer Rückgabewerttyp erforderlich ist, muss ein neuer Delegattyp deklariert werden.  
  
-   Instanziieren von Delegaten  
  
     Nachdem ein Delegattyp deklariert wurde, muss ein Delegatobjekt erstellt und mit einer bestimmten Methode verknüpft werden.  Im vorherigen Beispiel übergeben Sie dazu die `PrintTitle`\-Methode an die `ProcessPaperbackBooks`\-Methode, wie im folgenden Beispiel gezeigt:  
  
     [!code-cs[csProgGuideDelegates#17](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#17)]  
  
     Hierdurch wird ein neues Delegatobjekt erstellt, das mit der [static](../../../csharp/language-reference/keywords/static.md)\-Methode verknüpft ist `Test.PrintTitle`.  Auf ähnliche Weise wird die nicht statische `AddBookToTotal`\-Methode für das `totaller`\-Objekt wie im folgenden Beispiel übergeben:  
  
     [!code-cs[csProgGuideDelegates#18](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#18)]  
  
     In beiden Fällen wird ein neues Delegatobjekt an die `ProcessPaperbackBooks`\-Methode übergeben.  
  
     Nach der Erstellung eines Delegaten wird die mit diesem verknüpfte Methode nicht mehr geändert. Delegatobjekte sind unveränderlich.  
  
-   Aufrufen von Delegaten  
  
     Nachdem ein Delegatobjekt erstellt wurde, wird es normalerweise an anderen Code übergeben, durch den der Delegat aufgerufen wird.  Ein Delegatobjekt wird über seinen Namen aufgerufen. Auf den Namen folgen \(in Klammern gesetzte\) Argumente, die an den Delegaten übergeben werden sollen.  Es folgt ein Beispiel für einen Delegataufruf:  
  
     [!code-cs[csProgGuideDelegates#19](../../../csharp/programming-guide/delegates/codesnippet/csharp/csrefDelegates/Delegates.cs#19)]  
  
     Ein Delegat kann entweder \(wie in diesem Beispiel\) synchron oder mithilfe der `BeginInvoke`\-Methode und der `EndInvoke`\-Methode asynchron aufgerufen werden.  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)