---
title: Erstellen einer Aktivität zur Laufzeit mit DynamicActivity
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 0450a56059083f355f3fd71d95c83bf8dd1cf0e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a>Erstellen einer Aktivität zur Laufzeit mit DynamicActivity
<xref:System.Activities.DynamicActivity> ist eine konkrete, versiegelte Klasse mit einem öffentlichen Konstruktor. <xref:System.Activities.DynamicActivity> kann zur Zusammenstellung von Aktivitätsfunktionen zur Laufzeit mit einem Aktivitäts-DOM verwendet werden.  
  
## <a name="dynamicactivity-features"></a>DynamicActivity-Funktionen  
 <xref:System.Activities.DynamicActivity> hat Zugriff auf Ausführungseigenschaften, Argumente und Variablen, jedoch keinen Zugriff auf Laufzeitdienste, wie z. B. die Planung untergeordneter Aktivitäten oder die Nachverfolgung.  
  
 Eigenschaften der obersten Ebene können mit <xref:System.Activities.Argument>-Workflowobjekten festgelegt werden. In imperativem Code werden diese Argumente mittels CLR-Eigenschaften für einen neuen Typ erstellt. In XAML werden sie mit dem `x:Class`-Tag und dem `x:Member`-Tag deklariert.  
  
 Der Designer-Zugriff für die mit <xref:System.Activities.DynamicActivity> konstruierten Aktivitäten erfolgt über <xref:System.ComponentModel.ICustomTypeDescriptor>. Im Designer erstellte Aktivitäten können dynamisch mit <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> geladen werden, wie in der folgenden Prozedur veranschaulicht.  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a>So erstellen Sie zur Laufzeit eine Aktivität mit imperativem Code  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Wählen Sie **Datei**, **neue**, **Projekt**. Wählen Sie **Workflow 4.0** unter **Visual C#-** in der **Projekttypen** , und wählen Sie die **v2010** Knoten. Wählen Sie **Konsolenanwendung für sequenzielle Workflows** in der **Vorlagen** Fenster. Geben Sie dem neuen Projekt den Namen DynamicActivitySample.  
  
3.  Mit der rechten Maustaste Workflow1.xaml im HelloActivity-Projekt, und wählen Sie **löschen**.  
  
4.  Öffnen Sie die Datei Program.cs. Fügen Sie am Anfang der Datei die folgende Direktive hinzu.  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5.  Ersetzen Sie den Inhalt der `Main`-Methode durch den folgenden Code, mit dem eine <xref:System.Activities.Statements.Sequence>-Aktivität erstellt wird, die eine einzelne <xref:System.Activities.Statements.WriteLine>-Aktivität enthält. Diese wird der <xref:System.Activities.DynamicActivity.Implementation%2A>-Eigenschaft einer neuen dynamischen Aktivität zugewiesen.  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =   
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =   
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6.  Führen Sie die Anwendung aus. Ein Konsolenfenster mit dem Text "Hello World!" wird angezeigt.  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a>So erstellen Sie zur Laufzeit eine Aktivität mit XAML  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Wählen Sie **Datei**, **neue**, **Projekt**. Wählen Sie **Workflow 4.0** unter **Visual C#-** in der **Projekttypen** , und wählen Sie die **v2010** Knoten. Wählen Sie **Workflowkonsolenanwendung** in der **Vorlagen** Fenster. Geben Sie dem neuen Projekt den Namen DynamicActivitySample.  
  
3.  Öffnen Sie Workflow1.xaml im HelloActivity-Projekt. Klicken Sie auf die **Argumente** am unteren Rand des Designers die Option. Erstellen Sie ein neues `In`-Argument mit dem Namen `TextToWrite` und dem Typ `String`.  
  
4.  Ziehen Sie eine **WriteLine** Aktivität aus der **primitive** Abschnitt der Toolbox auf die Designeroberfläche. Weisen Sie den Wert `TextToWrite` auf die **Text** Eigenschaft der Aktivität.  
  
5.  Öffnen Sie die Datei Program.cs. Fügen Sie am Anfang der Datei die folgende Direktive hinzu.  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6.  Ersetzen Sie den Inhalt der `Main`-Methode durch folgenden Code.  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7.  Führen Sie die Anwendung aus. Ein Konsolenfenster mit dem Text "Hello World!" wird angezeigt.  
  
8.  Mit der rechten Maustaste in der Datei "Workflow1.xaml", in der **Projektmappen-Explorer** , und wählen Sie **Code anzeigen**. Beachten Sie, dass die Aktivitätsklasse mit `x:Class` und die Eigenschaft mit `x:Property` erstellt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)  
 [DynamicActivity-Erstellung](../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)
