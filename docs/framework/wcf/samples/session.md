---
title: Sitzung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
caps.latest.revision: "31"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e36666b72d14bbe257cd6ced8a35c360659a91dd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="session"></a>Sitzung
Das Sitzungsbeispiel führt vor, wie ein Vertrag implementiert wird, der eine Sitzung erfordert. Eine Sitzung bietet den Kontext zum Ausführen mehrerer Vorgänge. Dadurch wird ermöglicht, dass ein Dienst einer bestimmten Sitzung einen Zustand zuordnen kann, sodass nachfolgende Vorgänge den Zustand eines vorherigen Vorgangs verwenden können. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), implementiert einen rechnerdienst. Der `ICalculator`-Vertrag wurde so geändert, dass eine Reihe von arithmetischen Operationen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird. Diese Funktion wird vom `ICalculatorSession`-Vertrag definiert. Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst den Status für einen Client bei. Der Client kann das aktuelle Ergebnis abrufen, indem er `Result()` aufruft, und es auf Null löschen, indem er `Clear()` aufruft.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Durch Festlegen von <xref:System.ServiceModel.SessionMode> des Vertrags auf `Required` wird sichergestellt, dass – wenn der Vertrag über eine bestimmte Bindung verfügbar gemacht wird – die Bindung Sitzungen unterstützt. Wenn Sitzungen von der Bindung nicht unterstützt werden, wird eine Ausnahme ausgelöst. Die `ICalculatorSession`-Schnittstelle wird so definiert, dass ein oder mehrere Vorgänge aufgerufen werden können, die ein aktuelles Ergebnis ändern (siehe folgender Beispielcode).  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 Der Dienst verwendet einen <xref:System.ServiceModel.InstanceContextMode> von <xref:System.ServiceModel.InstanceContextMode.PerSession>, um an jede eingehende Sitzung einen bestimmten Dienstinstanzkontext zu binden. Dadurch wird dem Dienst ermöglicht, das aktuelle Ergebnis für jede Sitzung in einer lokalen Membervariablen beizubehalten.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
```  
  
 Beim Ausführen des Beispiels nimmt der Client mehrere Anforderungen am Server vor und fordert das Ergebnis ab, das dann im Clientkonsolenfenster angezeigt wird. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
  
## <a name="see-also"></a>Siehe auch
