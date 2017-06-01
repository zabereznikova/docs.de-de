---
title: "Benutzerdefinierte Aktivit&#228;t zum Aktivieren eines Wertebereichs | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Benutzerdefinierte Aktivit&#228;t zum Aktivieren eines Wertebereichs
Anhand dieses Beispiels wird veranschaulicht, wie eine benutzerdefinierte Aktivität, die die Verwendung eines <xref:System.Activities.Statements.Switch%601>\-Elements erweitert, erstellt wird.Eine herkömmliche <xref:System.Activities.Statements.Switch%601>\-Anweisung ermöglicht den auf einem einzelnen Wert basierenden Wechsel.In einigen Szenarios muss eine Aktivität jedoch basierend auf einem Wertebereich einen Wechsel ausführen.Beispiel: Eine Aktivität führt eine Aktion aus, wenn der Wert zwischen 1 und 5 liegt, eine andere Aktion, wenn der Wert zwischen 6 und 10 liegt, und eine Standardaktion für alle anderen Werte.Diese benutzerdefinierte Aktivität ermöglicht genau dieses Szenario.  
  
## Die SwitchRange\-Aktivität  
 Die `SwitchRange`\-Aktivität plant eine untergeordnete Aktivität, wenn der Ergebniswert des Ausdrucks innerhalb des Bereichs von einem der `Cases` liegt.  
  
 Das folgende Codebeispiel ist eine benutzerdefinierte Aktivität, die auf Basis eines Wertebereichs einen Wechsel ausführt.  
  
```csharp  
  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|||  
|-|-|  
|Eigenschaft|Beschreibung|  
|Ausdruck|Der Ausdruck, der ausgewertet und mit den Wertebereichen in der Cases\-Liste verglichen wird.Das Ergebnis dieses Ausdrucks ist vom Typ "T".|  
|Cases|Jeder "Fall" besteht aus einem Bereich \(Von\-Bis\) und einer Aktivität \(Text\).Der Ausdruck wird ausgewertet und mit den Wertebereichen verglichen.Wenn das Ergebnis des Ausdrucks innerhalb des Wertebereichs von einem der Fälle liegt, wird die entsprechende Aktivität ausgeführt.|  
|Default|Die Aktivität, die ausgeführt wird, wenn das Ergebnis mit keinem Fall in der Cases\-Liste übereinstimmt.Wenn Sie diese Eigenschaft auf `null` festlegen, wird keine Aktion ausgeführt.|  
  
## CaseRange\-Klasse  
 Die `CaseRange`\-Klasse stellt einen Bereich innerhalb einer `SwitchRange`\-Aktivität dar.Jede `CaseRange`\-Instanz enthält einen Wertebereich \(zwischen `From` und `To`\) und eine Aktivität \(`Body`\), die ausgeführt wird, wenn das Ergebnis des Ausdrucks der `SwitchRange`\-Aktivität innerhalb des Wertebereichs liegt.  
  
 Das folgende Codebeispiel stellt die Definition der `CaseRange`\-Klasse dar.  
  
```  
  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  Sowohl die `SwitchRange`\-Klasse als auch die `CaseRange`\-Klasse, die im Beispiel definiert werden, sind generische Klassen, die jeden Typ unterstützen, der `IComparable` implementiert, wie die <xref:System.Activities.Statements.Switch%601>\-Klasse.  
  
## Verwendungsbeispiel  
 Das folgende Codebeispiel zeigt, wie Sie die `SwitchRange`\-Aktivität verwenden.  
  
```csharp  
  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "SwitchRange.sln".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`  
  
## Siehe auch