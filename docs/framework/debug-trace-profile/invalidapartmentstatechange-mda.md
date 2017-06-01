---
title: "invalidApartmentStateChange MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "MDAs (managed debugging assistants), invalid apartment state"
  - "managed debugging assistants (MDAs), invalid apartment state"
  - "InvalidApartmentStateChange MDA"
  - "invalid apartment state changes"
  - "threading [.NET Framework], apartment states"
  - "apartment states"
  - "threading [.NET Framework], managed debugging assistants"
  - "COM apartment states"
ms.assetid: e56fb9df-5286-4be7-b313-540c4d876cd7
caps.latest.revision: 12
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 12
---
# invalidApartmentStateChange MDA
Der `invalidApartmentStateChange`\-MDA \(Managed Debugging Assistant, Assistent für verwaltetes Debuggen\) wird aktiviert, wenn eins der beiden folgenden Probleme auftritt:  
  
-   Es wird versucht, den COM\-Apartmentzustand eines Threads zu ändern, der von COM bereits für einen anderen Apartmentzustand initialisiert wurde.  
  
-   Der COM\-Apartmentzustand eines Threads ändert sich unerwartet.  
  
## Symptome  
  
-   Der COM\-Apartmentzustand eines Threads entspricht nicht dem angeforderten Zustand.  Als Folge davon werden möglicherweise Proxys für COM\-Komponenten verwendet, die ein vom aktuellen Threadmodell abweichendes Modell aufweisen.  Dies wiederum kann zum Auslösen einer <xref:System.InvalidCastException> führen, wenn das COM\-Objekt über Schnittstellen aufgerufen wird, die nicht für plattformübergreifendes Marshalling eingerichtet sind.  
  
-   Der COM\-Apartmentzustand des Threads ist anders als erwartet.  Dies kann zu einem <xref:System.Runtime.InteropServices.COMException> HRESULT mit dem Wert RPC\_E\_WRONG\_THREAD sowie zu einer <xref:System.InvalidCastException> führen, wenn Aufrufe in einen [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) \(RCW\) erfolgen.  Es kann auch dazu kommen, dass auf einige Singlethread\-COM\-Komponenten gleichzeitig durch mehrere Threads zugegriffen wird. Dies kann zur Beschädigung oder zum Verlust von Daten führen.  
  
## Ursache  
  
-   Der Thread wurde zuvor mit einem anderen COM\-Apartmentzustand initialisiert.  Beachten Sie, dass der Apartmentzustand eines Threads entweder explizit oder implizit festgelegt werden kann.  Zu den expliziten Vorgängen zählen die <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=fullName>\-Eigenschaft, die <xref:System.Threading.Thread.SetApartmentState%2A>\-Methode und die <xref:System.Threading.Thread.TrySetApartmentState%2A>\-Methode.  Für einen mit der <xref:System.Threading.Thread.Start%2A>\-Methode erstellten Thread wird implizit <xref:System.Threading.ApartmentState> festgelegt, es sei denn, vor dem Start des Threads wird <xref:System.Threading.Thread.SetApartmentState%2A> aufgerufen.  Wenn für die Hauptmethode nicht das <xref:System.STAThreadAttribute>\-Attribut angegeben wurde, wird der Hauptthread der Anwendung ebenfalls implizit als <xref:System.Threading.ApartmentState> initialisiert.  
  
-   Für den Thread wird die `CoUninitialize`\-Methode \(oder die `CoInitializeEx`\-Methode\) mit einem anderen Parallelitätsmodell aufgerufen.  
  
## Lösung  
 Legen Sie den Apartmentzustand des Threads vor dem Start der Ausführung fest, oder wenden Sie auf die Hauptmethode der Anwendung entweder das <xref:System.STAThreadAttribute>\-Attribut oder das <xref:System.MTAThreadAttribute>\-Attribut an.  
  
 Für die zweite Ursache sollte der Code, in dem die `CoUninitialize`\-Methode aufgerufen wird, am besten so geändert werden, dass der Aufruf verzögert wird, bis der Thread kurz vor dem Beenden steht und keine der von ihm verwendeten RCWs oder der entsprechenden zugrunde liegenden COM\-Komponenten mehr in Gebrauch sind.  Wenn jedoch der die `CoUninitialize`\-Methode aufrufende Code nicht geändert werden kann, dürfen keine RCWs aus Threads verwendet werden, die auf diese Weise deinitialisiert werden.  
  
## Auswirkungen auf die Laufzeit  
 Dieser MDA hat keine Auswirkungen auf die CLR.  
  
## Ausgabe  
 Der COM\-Apartmentzustand des aktuellen Threads und der Zustand, der durch den Code angewendet werden sollte.  
  
## Konfiguration  
  
```  
<mdaConfig>  
  <assistants>  
    <invalidApartmentStateChange />  
  </assistants>  
</mdaConfig>  
```  
  
## Beispiel  
 Im folgenden Codebeispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann.  
  
```  
using System.Threading;  
namespace ApartmentStateMDA  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            Thread.CurrentThread.SetApartmentState(ApartmentState.STA);  
        }  
    }  
}  
```  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)   
 [Interop Marshaling](../../../docs/framework/interop/interop-marshaling.md)