---
title: "Gewusst wie: Abonnieren von Ereignissen und K&#252;ndigen von Ereignisabonnements (C#-Programmierhandbuch) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Code-Editor, Ereignishandler"
  - "Ereignishandler [C#], Erstellen"
  - "Ereignisse [C#], Erstellen mit der IDE"
ms.assetid: 6319f39f-282c-4173-8a62-6c4657cf51cd
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Gewusst wie: Abonnieren von Ereignissen und K&#252;ndigen von Ereignisabonnements (C#-Programmierhandbuch)
Es empfiehlt sich, ein von einer anderen Klasse veröffentlichtes Ereignis zu abonnieren, wenn Sie benutzerdefinierten Code schreiben möchten, der aufgerufen wird, sobald das Ereignis ausgelöst wird.  Beispielsweise können Sie das `click`\-Ereignis einer Schaltfläche abonnieren, damit die Anwendung eine sinnvolle Aktion ausführt, wenn der Benutzer auf die Schaltfläche klickt.  
  
### So abonnieren Sie Ereignisse mit der Visual Studio IDE  
  
1.  Wenn das Fenster **Eigenschaften** nicht sichtbar ist, klicken Sie in der **Entwurfsansicht** mit der rechten Maustaste auf das Formular oder Steuerelement, für das Sie einen Ereignishandler erstellen möchten, und wählen Sie **Eigenschaften**.  
  
2.  Klicken Sie oben im Fenster **Eigenschaften** auf das Symbol **Ereignisse**.  
  
3.  Doppelklicken Sie auf das Ereignis, das Sie erstellen möchten, z. B. das `Load`\-Ereignis.  
  
     [!INCLUDE[csprcs](../../../csharp/includes/csprcs-md.md)] erstellt eine leere Ereignishandlermethode und fügt diese dem Code hinzu.  Sie können den Code auch in der **Codeansicht** manuell hinzufügen.  Die folgenden Codezeilen deklarieren z. B. eine Ereignishandlermethode, die aufgerufen wird, wenn die `Form`\-Klasse das `Load`\-Ereignis auslöst.  
  
     [!code-cs[csProgGuideEvents#11](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-subscribe-to-and-unsubscribe-from-events_1.cs)]  
  
     Die Codezeile, die zum Abonnieren des Ereignisses erforderlich ist, wird automatisch in der `InitializeComponent`\-Methode der Projektdatei Form1.Designer.cs generiert.  Sie sieht etwa so aus:  
  
    ```  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
### So abonnieren Sie Ereignisse programmgesteuert  
  
1.  Definieren Sie eine Ereignishandlermethode, deren Signatur mit der Delegatsignatur für das Ereignis übereinstimmt.  Wenn das Ereignis beispielsweise auf dem <xref:System.EventHandler>\-Delegattyp basiert, entspricht der folgende Code dem Methodenstub:  
  
    ```  
    void HandleCustomEvent(object sender, CustomEventArgs a)  
    {  
       // Do something useful here.  
    }  
    ```  
  
2.  Verwenden Sie den Additionszuweisungsoperator \(`+=`\), um den Ereignishandler mit dem Ereignis zu verknüpfen.  Im folgenden Beispiel wird angenommen, dass ein Objekt mit dem Namen `publisher` über ein Ereignis mit dem Namen `RaiseCustomEvent` verfügt.  Beachten Sie, dass die Abonnentenklasse einen Verweis auf die Herausgeberklasse benötigt, um die Ereignisse zu abonnieren.  
  
    ```  
    publisher.RaiseCustomEvent += HandleCustomEvent;  
    ```  
  
     Beachten Sie, dass die oben dargestellte Syntax in C\# 2.0 neu ist.  Sie stimmt exakt mit der C\# 1.0\-Syntax überein, in der der Kapselungsdelegat mit dem `new`\-Schlüsselwort explizit erstellt werden muss:  
  
    ```  
    publisher.RaiseCustomEvent += new CustomEventHandler(HandleCustomEvent);  
    ```  
  
     Ein Ereignishandler kann auch mit einem Lambda\-Ausdruck hinzugefügt werden:  
  
    ```  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
        this.Click += (s,e) => { MessageBox.Show(  
           ((MouseEventArgs)e).Location.ToString());};  
    }  
    ```  
  
     Weitere Informationen hierzu finden Sie unter [Gewusst wie: Verwenden von Lambda\-Ausdrücken außerhalb von LINQ](../../../csharp/programming-guide/statements-expressions-operators/how-to-use-lambda-expressions-outside-linq.md).  
  
### So abonnieren Sie Ereignisse mit einer anonymen Methode  
  
-   Wenn Sie nicht zu einem späteren Zeitpunkt ein Abonnement für ein Ereignis kündigen müssen, können Sie dem Ereignis mit dem Additionszuweisungsoperator \(`+=`\) eine anonyme Methode zuweisen.  Im folgenden Beispiel wird angenommen, dass ein Objekt mit dem Namen `publisher` über ein Ereignis mit dem Namen `RaiseCustomEvent`  verfügt und dass eine `CustomEventArgs`\-Klasse definiert wurde, die spezielle Ereignisinformationen enthält.  Beachten Sie, dass die Abonnentenklasse einen Verweis auf `publisher` benötigt, um die Ereignisse zu abonnieren.  
  
    ```  
    publisher.RaiseCustomEvent += delegate(object o, CustomEventArgs e)  
    {  
      string s = o.ToString() + " " + e.ToString();  
      Console.WriteLine(s);  
    };  
    ```  
  
     Beachten Sie, dass ein Abonnement für ein Ereignis nicht leicht gekündigt werden kann, wenn Sie es mit der anonymen Funktion abonniert haben.  Um in diesem Szenario ein Abonnement zu kündigen, müssen Sie zu dem Code zurückkehren, mit dem Sie das Ereignis abonniert haben, die anonyme Methode in einer Delegatvariablen speichern und anschließend dem Ereignis den Delegaten hinzufügen.  Im Allgemeinen empfehlen wir, keine anonymen Funktionen zum Abonnieren von Ereignissen zu verwenden, wenn Sie das Abonnement des Ereignisses zu einem späteren Zeitpunkt im Code kündigen müssen.  Weitere Informationen über anonyme Funktionen finden Sie unter [Anonyme Funktionen](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md).  
  
## Kündigen des Abonnements  
 Wenn Sie nicht möchten, dass der Ereignishandler aufgerufen wird, wenn das Ereignis ausgelöst wird, müssen Sie das Abonnement für das Ereignis kündigen.  Um Ressourcenverluste zu verhindern, ist es wichtig, Abonnements für Ereignisse zu kündigen, bevor Sie ein Abonnentenobjekt entfernen.  Solange ein Abonnement für ein Ereignis nicht gekündigt wird, unterliegt der Multicastdelegat dem Ereignis im Veröffentlichungsobjekt, das auf den Delegaten verweist, der den Ereignishandler des Abonnenten kapselt.  Das Abonnentenobjekt wird erst aus der Garbage Collection gelöscht, wenn der Verweis aus dem Veröffentlichungsobjekt entfernt wurde.  
  
#### So kündigen Sie ein Abonnement für ein Ereignis  
  
-   Verwenden Sie den Subtraktionszuweisungsoperator \(`-=`\), um ein Abonnement für ein Ereignis zu kündigen:  
  
    ```  
    publisher.RaiseCustomEvent -= HandleCustomEvent;  
    ```  
  
     Wenn alle Abonnenten ihre Abonnements für ein Ereignis gekündigt haben, wird die Ereignisinstanz in der Herausgeberklasse auf `null` festgelegt.  
  
## Siehe auch  
 [Ereignisse](../../../csharp/programming-guide/events/index.md)   
 [event](../../../csharp/language-reference/keywords/event.md)   
 [Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework\-Richtlinien entsprechen](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md)   
 [Operator \-\=](../../../csharp/language-reference/operators/subtraction-assignment-operator-1.md)   
 [Operator \+\=](../../../csharp/language-reference/operators/addition-assignment-operator.md)