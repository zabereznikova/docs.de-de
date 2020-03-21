---
title: Sitzung
ms.date: 03/30/2017
helpviewer_keywords:
- Sessions
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
ms.openlocfilehash: 85f1034999fc4cd36075c49bd8f4631bbd283679
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183362"
---
# <a name="session"></a>Sitzung
Das Sitzungsbeispiel führt vor, wie ein Vertrag implementiert wird, der eine Sitzung erfordert. Eine Sitzung bietet den Kontext zum Ausführen mehrerer Vorgänge. Dadurch wird ermöglicht, dass ein Dienst einer bestimmten Sitzung einen Zustand zuordnen kann, sodass nachfolgende Vorgänge den Zustand eines vorherigen Vorgangs verwenden können. Dieses Beispiel basiert auf dem [Ersten Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das einen Rechnerdienst implementiert. Der `ICalculator`-Vertrag wurde so geändert, dass eine Reihe von arithmetischen Operationen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird. Diese Funktion wird vom `ICalculatorSession`-Vertrag definiert. Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst den Status für einen Client bei. Der Client kann das aktuelle Ergebnis abrufen, indem er `Result()` aufruft, und es auf Null löschen, indem er `Clear()` aufruft.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Durch Festlegen von <xref:System.ServiceModel.SessionMode> des Vertrags auf `Required` wird sichergestellt, dass – wenn der Vertrag über eine bestimmte Bindung verfügbar gemacht wird – die Bindung Sitzungen unterstützt. Wenn Sitzungen von der Bindung nicht unterstützt werden, wird eine Ausnahme ausgelöst. Die `ICalculatorSession`-Schnittstelle wird so definiert, dass ein oder mehrere Vorgänge aufgerufen werden können, die ein aktuelles Ergebnis ändern (siehe folgender Beispielcode).  
  
```csharp
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
  
```csharp
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
  
```console  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
