---
title: "Festlegen der Use-Eigenschaft und der Style-Eigenschaft | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# Festlegen der Use-Eigenschaft und der Style-Eigenschaft
In diesem Beispiel wird die Verwendung der Use\-Eigenschaft und der Style\-Eigenschaft in <xref:System.ServiceModel.XmlSerializerFormatAttribute> und <xref:System.ServiceModel.DataContractFormatAttribute> veranschaulicht.  Diese Eigenschaften beeinflussen die Formatierung von Nachrichten.  Standardmäßig wird der Nachrichtentext mit dem auf <xref:System.ServiceModel.OperationFormatStyle> festgelegten Format formatiert.  Diese Einstellungen können entweder auf der Dienstvertragsebene oder der Vorgangsvertragsebene angegeben werden.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A>\-Stileigenschaft bestimmt, wie die WSDL\-Metadaten für den Dienst formatiert werden.  Mögliche Werte sind <xref:System.ServiceModel.OperationFormatStyle> und <xref:System.ServiceModel.OperationFormatStyle>.  RPC bedeutet, dass die WSDL\-Darstellung von Nachrichten, die für einen Vorgang ausgetauscht wurden, Parameter entsprechend einem Remoteprozeduraufruf enthält.  Nachfolgend finden Sie ein Beispiel:  
  
```  
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">  
    <wsdl:part name="n1" type="xsd:double"/>  
    <wsdl:part name="n2" type="xsd:double"/>  
</wsdl:message>  
```  
  
 Das Format auf <xref:System.ServiceModel.OperationFormatStyle> festzulegen, bedeutet, dass die WSDL\-Darstellung ein einzelnes Element enthält, das das gegen einen Vorgang ausgetauschte Dokument darstellt. Dies ist im folgenden Beispiel veranschaulicht.  
  
```  
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">  
    <wsdl:part name="parameters" element="tns:Add"/>  
</wsdl:message>  
```  
  
 Die <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A>\-Eigenschaft bestimmt das Format der Nachricht.  Mögliche Werte sind <xref:System.ServiceModel.OperationFormatUse> und <xref:System.ServiceModel.OperationFormatUse>. Der Standardwert ist <xref:System.ServiceModel.OperationFormatUse>.  Literal bedeutet, dass die Nachricht eine Literalinstanz des Schemas in der WSDL ist, wie im folgenden Dokument\-\/Literal\-Beispiel dargestellt.  
  
```  
<Add xmlns="http://Microsoft.ServiceModel.Samples">  
    <n1>100</n1>  
    <n2>15.99</n2>  
</Add>  
```  
  
 Encoded bedeutet, dass die Schemen in der WSDL abstrakte Spezifikationen sind, die gemäß den Regeln in SOAP 1.1, Abschnitt 5 codiert werden.  Es folgt ein RPC\/Encoded\-Beispiel.  
  
```  
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">  
    <n1 xsi:type="xsd:double" xmlns="">100</n1>  
    <n2 xsi:type="xsd:double" xmlns="">15.99</n2>  
</q1:Add>  
```  
  
 WS\-I Basic Profile 1.0 verbietet die Verwendung von <xref:System.ServiceModel.OperationFormatUse>. Sie sollten dies daher nur verwenden, wenn es aufgrund von älteren Diensten erforderlich ist.  Das `Encoded`\-Nachrichtenformat ist nur bei Verwendung von XmlSerializer verfügbar.  
  
 Damit Sie die gesendeten und empfangenen Nachrichten anzeigen können, basiert dieses Beispiel auf [Ablaufverfolgung und Nachrichtenprotokollierung](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  Die Dienstkonfiguration und der Quellcode wurden geändert, um Ablaufverfolgung und Nachrichtenprotokollierung zu aktivieren und zu verwenden.  Außerdem wurde <xref:System.ServiceModel.WsHttpBinding> ohne Sicherheit konfiguriert, sodass protokollierte Nachrichten in einem unverschlüsselten Format angezeigt werden können.  Die resultierenden Ablaufverfolgungsprotokolle \(System.ServiceModel.e2e und Message.log\) sollten mit [Service Trace Viewer\-Tool \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) angezeigt werden.  Die Ablaufverfolgungen sind so konfiguriert, dass sie im Ordner C:\\LOGS erstellt werden.  Erstellen Sie den Ordner vor dem Ausführen des Beispiels.  Wählen Sie zum Anzeigen der Nachrichteninhalte im Service Trace Viewer\-Tool im linken und rechten Bereich **Meldungen** aus.  
  
 Im folgenden Code wird der Dienstvertrag veranschaulicht, wobei die <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A>\-Eigenschaft auf <xref:System.ServiceModel.OperationFormatUse> festgelegt und das Format des Nachrichtentexts vom Standard \(<xref:System.ServiceModel.OperationFormatStyle>\) in <xref:System.ServiceModel.OperationFormatStyle> geändert wurde.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
XmlSerializerFormat(Style = OperationFormatStyle.Rpc,   
                                 Use = OperationFormatUse.Encoded)]  
public interface IUseAndStyleCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 Um den Unterschied zwischen den unterschiedlichen Einstellungen für <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> und <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> zu verdeutlichen, ändern Sie sie im Dienst, generieren Sie den Client erneut, führen Sie das Beispiel aus, und betrachten Sie dann die Datei "c:\\logs\\message.logs" im Service Trace Viewer\-Tool.  Beachten Sie auch die Auswirkungen auf die Metadaten, indem Sie http:\/\/localhost\/ServiceModelSamples\/service.svc?wsdl anzeigen.  Die Metadaten für Dienste sind normalerweise in mehrere Seiten untergeteilt.  Die wsdl\-Hauptseite enthält die WSDL\-Bindungen, zeigen Sie jedoch http:\/\/localhost\/ServiceModelSamples\/service.svc?wsdl\=wsdl0 an, um die Nachrichtendefinitionen zu betrachten.  
  
### So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie die [Einmaliges Setupverfahren für Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) ausgeführt haben.  
  
2.  Erstellen Sie zum Protokollieren von Nachrichten das Verzeichnis C:\\LOGS.  Weisen Sie dem Benutzer Network Service die Schreibberechtigung für dieses Verzeichnis zu.  
  
3.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
4.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`  
  
## Siehe auch