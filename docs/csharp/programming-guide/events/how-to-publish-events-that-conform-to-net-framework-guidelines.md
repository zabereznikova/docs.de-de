---
title: "Gewusst wie: Ver&#246;ffentlichen von Ereignissen, die den .NET&#160;Framework-Richtlinien entsprechen (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Ereignisse [C#], Implementierungsrichtlinien"
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
caps.latest.revision: 31
caps.handback.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Ver&#246;ffentlichen von Ereignissen, die den .NET&#160;Framework-Richtlinien entsprechen (C#-Programmierhandbuch)
Das folgende Verfahren veranschaulicht, wie Sie den Klassen und Strukturen Ereignisse hinzufügen, die dem Standardmuster von [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] entsprechen.  Sämtliche Ereignisse in der [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Klassenbibliothek basieren auf dem <xref:System.EventHandler>\-Delegat, der folgendermaßen definiert ist:  
  
```  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong-md.md)] führt eine generische Version dieses Delegaten ein, <xref:System.EventHandler%601>.  Die folgenden Beispiele zeigen die Verwendung beider Versionen.  
  
 Grundsätzlich können Ereignisse in benutzerdefinierten Klassen auf jedem gültigen Delegattyp basieren, einschließlich Delegaten, die einen Wert zurückgeben. Im Allgemeinen wird jedoch empfohlen, Ereignisse auf dem [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Muster zu basieren, indem Sie <xref:System.EventHandler> verwenden, wie im folgenden Beispiel gezeigt:  
  
### So veröffentlichen Sie Ereignisse auf Basis des EventHandler\-Musters  
  
1.  \(Wenn Sie keine benutzerdefinierten Daten mit dem Ereignis senden müssen, können Sie diesen Schritt überspringen und mit Schritt 3a fortfahren.\) Deklarieren Sie die Klasse für die benutzerdefinierten Daten mit einem Bereich, der sowohl für die Herausgeber\- als auch die Abonnentenklasse sichtbar ist.  Fügen Sie dann die erforderlichen Member zum Speichern der benutzerdefinierten Ereignisdaten hinzu.  In diesem Beispiel wird eine einfache Zeichenfolge zurückgegeben.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
2.  \(Wenn Sie die generische Version von <xref:System.EventHandler%601> verwenden, können Sie diesen Schritt überspringen.\) Deklarieren Sie einen Delegaten in der Veröffentlichungsklasse.  Weisen Sie ihm einen Namen zu, der auf *EventHandler* endet.  Der zweite Parameter gibt den benutzerdefinierten EventArgs\-Typ an.  
  
    ```  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3.  Deklarieren Sie das Ereignis in der Veröffentlichungsklasse mit einem der folgenden Schritte.  
  
    1.  Wenn Sie über keine benutzerdefinierte EventArgs\-Klasse verfügen, entspricht der Ereignistyp dem nicht generischen EventHandler\-Delegaten.  Sie müssen den Delegaten nicht deklarieren, da er bereits in dem standardmäßig in C\#\-Projekten enthaltenen <xref:System>\-Namespace deklariert ist.  Fügen Sie der Herausgeberklasse folgenden Code hinzu:  
  
        ```  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  Wenn Sie die nicht generische Version von <xref:System.EventHandler> verwenden und über eine benutzerdefinierte Klasse verfügen, die von <xref:System.EventArgs> abgeleitet wurde, deklarieren Sie das Ereignis in der Veröffentlichungsklasse, und verwenden Sie den Delegaten aus Schritt 2 als Typ.  
  
        ```  
        public event CustomEventHandler RaiseCustomEvent;  
  
        ```  
  
    3.  Wenn Sie die generische Version verwenden, benötigen Sie keinen benutzerdefinierten Delegaten.  Stattdessen geben Sie in der Veröffentlichungsklasse den Ereignistyp mit `EventHandler<CustomEventArgs>` an, mit dem Namen Ihrer Klasse zwischen den spitzen Klammern.  
  
        ```  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die oben beschriebenen Schritte anhand einer benutzerdefinierten EventArgs\-Klasse und des Ereignistyps <xref:System.EventHandler%601>.  
  
 [!code-cs[csProgGuideEvents#2](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-publish-events-that-_1.cs)]  
  
## Siehe auch  
 <xref:System.Delegate>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ereignisse](../../../csharp/programming-guide/events/index.md)   
 [Delegaten](../../../csharp/programming-guide/delegates/index.md)