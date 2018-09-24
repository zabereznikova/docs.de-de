---
title: 'Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], implementation guidelines
ms.assetid: 9310ae16-8627-44a2-b08c-05e5976202b1
ms.openlocfilehash: 9a17aaec20b03325abadfcc168f7ac4653f300df
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46576755"
---
# <a name="how-to-publish-events-that-conform-to-net-framework-guidelines-c-programming-guide"></a>Gewusst wie: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen (C#-Programmierhandbuch)
Das folgende Verfahren veranschaulicht, wie Sie Ereignisse hinzufügen können, die dem [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Standardmuster ihrer Klassen und Strukturen folgen. Alle Ereignisse in der [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Klassenbibliothek basieren auf dem <xref:System.EventHandler>-Delegaten, der wie folgt definiert ist:  
  
```csharp  
public delegate void EventHandler(object sender, EventArgs e);  
```  
  
> [!NOTE]
>  Das [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)] führt eine generische Version dieses Delegaten ein: <xref:System.EventHandler%601>. Die folgenden Beispiele zeigen, wie Sie beide Versionen verwenden können.  
  
 Auch wenn Ereignisse in von Ihnen definierten Klassen auf jedem beliebigen Delegattyp basiert sein können – sogar Delegate, die einen Wert zurückgeben –, wird allgemein empfohlen, dass Sie Ihre Ereignisse mit dem <xref:System.EventHandler> auf dem [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]-Muster basieren, wie in folgendem Beispiel gezeigt.  
  
### <a name="to-publish-events-based-on-the-eventhandler-pattern"></a>So veröffentlichen Sie Ereignisse, die auf dem EventHandler-Muster basieren  
  
1.  (Überspringen Sie diesen Schritt, und gehen Sie direkt zu Schritt 3a, wenn Sie keine benutzerdefinierten Daten mit Ihrem Ereignis senden müssen.) Deklarieren Sie die Klasse Ihrer benutzerdefinierten Daten in einem für Ihre Herausgeber- und Ihre Abonnentenklasse sichtbaren Geltungsbereich. Fügen Sie dann die erforderlichen Member hinzu, die Ihre benutzerdefinierten Ereignisdaten enthalten sollen. In diesem Beispiel wird eine einzelne Zeichenfolge zurückgegeben.  
  
    ```csharp  
    public class CustomEventArgs : EventArgs  
    {  
        public CustomEventArgs(string s)  
        {  
            msg = s;  
        }  
        private string msg;  
        public string Message  
        {  
            get { return msg; }  
        }   
    }  
    ```  
  
2.  (Überspringen Sie diesen Schritt, wenn Sie eine generische Version von <xref:System.EventHandler%601> verwenden.) Deklarieren Sie einen Delegaten in Ihrer Herausgeberklasse. Geben Sie ihm einen Namen, der auf *EventHandler* endet. Der zweite Parameter gibt Ihren benutzerdefinierten EventArgs-Typen an.  
  
    ```csharp  
    public delegate void CustomEventHandler(object sender, CustomEventArgs a);  
    ```  
  
3.  Deklarieren Sie das Ereignis in Ihrer Herausgeberklasse, indem Sie einen der folgenden Schritte verwenden.  
  
    1.  Wenn Sie keine benutzerdefinierte EventArgs-Klasse haben, ist Ihr Ereignistyp der nicht generische EventHandler-Delegat. Sie müssen den Delegaten nicht deklarieren, da er schon im <xref:System>-Namespace deklariert wurde, der bei der Erstellung Ihres C#-Projekts erstellt wird. Fügen Sie den folgenden Code in Ihre Herausgeberklasse ein.  
  
        ```csharp  
        public event EventHandler RaiseCustomEvent;  
        ```  
  
    2.  Wenn Sie die nicht generische Version von <xref:System.EventHandler> verwenden, und Sie eine benutzerdefinierte Klasse haben, die von <xref:System.EventArgs> abgeleitet ist, deklarieren Sie Ihr Ereignis innerhalb Ihrer Herausgeberklasse, und verwenden Sie Ihren Delegaten aus Schritt 2 als Typ.  
  
        ```csharp  
        public event CustomEventHandler RaiseCustomEvent;  
        ```  
  
    3.  Wenn sie die generische Version verwenden, benötigen Sie keinen benutzerdefinierten Delegaten. Stattdessen geben Sie in Ihrer Herausgeberklasse Ihren Ereignistypen als `EventHandler<CustomEventArgs>` an und fügen den Namen Ihrer eigenen Klasse in die eckigen Klammern ein.  
  
        ```csharp  
        public event EventHandler<CustomEventArgs> RaiseCustomEvent;  
        ```  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die oben genannten Schritte durch das Verwenden von einer benutzerdefinierten EventArgs-Klasse und von <xref:System.EventHandler%601> als Ereignistyp.  
  
 [!code-csharp[csProgGuideEvents#2](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-publish-events-that-conform-to-net-framework-guidelines_1.cs)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Delegate>  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [Ereignisse](../../../csharp/programming-guide/events/index.md)  
- [Delegaten](../../../csharp/programming-guide/delegates/index.md)
