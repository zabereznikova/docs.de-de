---
title: "Sitzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Sitzungen"
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
caps.latest.revision: 31
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 31
---
# Sitzung
Das Sitzungsbeispiel führt vor, wie ein Vertrag implementiert wird, der eine Sitzung erfordert.Eine Sitzung bietet den Kontext zum Ausführen mehrerer Vorgänge.Dadurch wird ermöglicht, dass ein Dienst einer bestimmten Sitzung einen Zustand zuordnen kann, sodass nachfolgende Vorgänge den Zustand eines vorherigen Vorgangs verwenden können.Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), das einen Rechnerdienst implementiert.Der `ICalculator`\-Vertrag wurde so geändert, dass eine Reihe von arithmetischen Operationen ausgeführt werden kann, während ein Zwischenergebnis aufbewahrt wird.Diese Funktion wird vom `ICalculatorSession`\-Vertrag definiert.Während mehrere Dienstvorgänge zum Ausführen einer Berechnung aufgerufen werden, behält der Dienst den Status für einen Client bei.Der Client kann das aktuelle Ergebnis abrufen, indem er `Result()` aufruft, und es auf Null löschen, indem er `Clear()` aufruft.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung \(.exe\), und der Dienst wird von IIS gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Erstellungsanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Durch Festlegen von <xref:System.ServiceModel.SessionMode> des Vertrags auf `Required` wird sichergestellt, dass – wenn der Vertrag über eine bestimmte Bindung verfügbar gemacht wird – die Bindung Sitzungen unterstützt.Wenn Sitzungen von der Bindung nicht unterstützt werden, wird eine Ausnahme ausgelöst.Die `ICalculatorSession`\-Schnittstelle wird so definiert, dass ein oder mehrere Vorgänge aufgerufen werden können, die ein aktuelles Ergebnis ändern \(siehe folgender Beispielcode\).  
  
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
  
 Der Dienst verwendet einen <xref:System.ServiceModel.InstanceContextMode> von <xref:System.ServiceModel.InstanceContextMode>, um an jede eingehende Sitzung einen bestimmten Dienstinstanzkontext zu binden.Dadurch wird dem Dienst ermöglicht, das aktuelle Ergebnis für jede Sitzung in einer lokalen Membervariablen beizubehalten.  
  
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
  
 Beim Ausführen des Beispiels nimmt der Client mehrere Anforderungen am Server vor und fordert das Ergebnis ab, das dann im Clientkonsolenfenster angezeigt wird.Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Folgen Sie zum Erstellen der C\#\- bzw. Visual Basic .NET\-Version der Projektmappe den Anweisungen unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
  
## Siehe auch