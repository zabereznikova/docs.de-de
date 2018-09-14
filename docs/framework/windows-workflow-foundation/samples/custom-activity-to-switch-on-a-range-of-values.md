---
title: Benutzerdefinierte Aktivität zum Aktivieren eines Wertebereichs
ms.date: 03/30/2017
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
ms.openlocfilehash: cfaf4318b1557a9fc217de8254e164243ea54569
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45616350"
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a>Benutzerdefinierte Aktivität zum Aktivieren eines Wertebereichs
Anhand dieses Beispiels wird veranschaulicht, wie eine benutzerdefinierte Aktivität, die die Verwendung eines <xref:System.Activities.Statements.Switch%601>-Elements erweitert, erstellt wird. Eine herkömmliche <xref:System.Activities.Statements.Switch%601>-Anweisung ermöglicht den auf einem einzelnen Wert basierenden Wechsel. In einigen Szenarios muss eine Aktivität jedoch basierend auf einem Wertebereich einen Wechsel ausführen. Beispiel: Eine Aktivität führt eine Aktion aus, wenn der Wert zwischen 1 und 5 liegt, eine andere Aktion, wenn der Wert zwischen 6 und 10 liegt, und eine Standardaktion für alle anderen Werte. Diese benutzerdefinierte Aktivität ermöglicht genau dieses Szenario.  
  
## <a name="the-switchrange-activity"></a>Die SwitchRange-Aktivität  
 Die `SwitchRange`-Aktivität plant eine untergeordnete Aktivität, wenn der Ergebniswert des Ausdrucks innerhalb des Bereichs von einem der `Cases` liegt.  
  
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
  
|Eigenschaft|Beschreibung|  
|-|-|  
|Ausdruck|Der Ausdruck, der ausgewertet und mit den Wertebereichen in der Cases-Liste verglichen wird. Das Ergebnis dieses Ausdrucks ist vom Typ "T".|  
|Cases|Jeder "Fall" besteht aus einem Bereich (Von-Bis) und einer Aktivität (Text). Der Ausdruck wird ausgewertet und mit den Wertebereichen verglichen. Wenn das Ergebnis des Ausdrucks innerhalb des Wertebereichs von einem der Fälle liegt, wird die entsprechende Aktivität ausgeführt.|  
|Standard|Die Aktivität, die ausgeführt wird, wenn das Ergebnis mit keinem Fall in der Cases-Liste übereinstimmt. Wenn Sie diese Eigenschaft auf `null` festlegen, wird keine Aktion ausgeführt.|  
  
## <a name="caserange-class"></a>CaseRange-Klasse  
 Die `CaseRange`-Klasse stellt einen Bereich innerhalb einer `SwitchRange`-Aktivität dar. Jede `CaseRange`-Instanz enthält einen Wertebereich (zwischen `From` und `To`) und eine Aktivität (`Body`), die ausgeführt wird, wenn das Ergebnis des Ausdrucks der `SwitchRange`-Aktivität innerhalb des Wertebereichs liegt.  
  
 Das folgende Codebeispiel stellt die Definition der `CaseRange`-Klasse dar.  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  Sowohl die `SwitchRange`-Klasse als auch die `CaseRange`-Klasse, die im Beispiel definiert werden, sind generische Klassen, die jeden Typ unterstützen, der `IComparable` implementiert, wie die <xref:System.Activities.Statements.Switch%601>-Klasse.  
  
## <a name="sample-usage"></a>Verwendung des Beispiels  
 Das folgende Codebeispiel zeigt, wie Sie die `SwitchRange`-Aktivität verwenden.  
  
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
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "SwitchRange.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`