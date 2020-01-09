---
title: Festlegen der Beispiele für Verwendung und Stileigenschaften
ms.date: 03/30/2017
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
ms.openlocfilehash: 36111aa05680fb8b369cde6b42d22c9c3b8474ad
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345133"
---
# <a name="setting-the-use-and-style-properties"></a>Festlegen der Use-Eigenschaft und der Style-Eigenschaft

In diesem Beispiel wird die Verwendung der Use-Eigenschaft und der Style-Eigenschaft in <xref:System.ServiceModel.XmlSerializerFormatAttribute> und <xref:System.ServiceModel.DataContractFormatAttribute> veranschaulicht. Diese Eigenschaften beeinflussen die Formatierung von Nachrichten. Standardmäßig wird der Nachrichtentext mit dem auf <xref:System.ServiceModel.OperationFormatStyle.Document> festgelegten Format formatiert. Diese Einstellungen können entweder auf der Dienstvertragsebene oder der Vorgangsvertragsebene angegeben werden.

> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.

Die <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A>-Stileigenschaft bestimmt, wie die WSDL-Metadaten für den Dienst formatiert werden. Mögliche Werte sind <xref:System.ServiceModel.OperationFormatStyle.Document> und <xref:System.ServiceModel.OperationFormatStyle.Rpc>. RPC bedeutet, dass die WSDL-Darstellung von Nachrichten, die für einen Vorgang ausgetauscht wurden, Parameter entsprechend einem Remoteprozeduraufruf enthält. Nachfolgend finden Sie ein Beispiel:

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="n1" type="xsd:double"/>
  <wsdl:part name="n2" type="xsd:double"/>
</wsdl:message>
```

Das Format auf <xref:System.ServiceModel.OperationFormatStyle.Document> festzulegen, bedeutet, dass die WSDL-Darstellung ein einzelnes Element enthält, das das gegen einen Vorgang ausgetauschte Dokument darstellt. Dies ist im folgenden Beispiel veranschaulicht.

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="parameters" element="tns:Add"/>
</wsdl:message>
```

Die <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A>-Eigenschaft bestimmt das Format der Nachricht. Mögliche Werte sind <xref:System.ServiceModel.OperationFormatUse.Literal> und <xref:System.ServiceModel.OperationFormatUse.Encoded>. Der Standardwert ist <xref:System.ServiceModel.OperationFormatUse.Literal>. Literal bedeutet, dass die Nachricht eine Literalinstanz des Schemas in der WSDL ist, wie im folgenden Dokument-/Literal-Beispiel dargestellt.

```xml
<Add xmlns="http://Microsoft.ServiceModel.Samples">
  <n1>100</n1>
  <n2>15.99</n2>
</Add>
```

Encoded bedeutet, dass die Schemen in der WSDL abstrakte Spezifikationen sind, die gemäß den Regeln in SOAP 1.1, Abschnitt 5 codiert werden. Es folgt ein RPC/Encoded-Beispiel.

```xml
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">
  <n1 xsi:type="xsd:double" xmlns="">100</n1>
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>
</q1:Add>
```

WS-I Basic Profile 1.0 verbietet die Verwendung von <xref:System.ServiceModel.OperationFormatUse.Encoded>. Sie sollten dies daher nur verwenden, wenn es aufgrund von älteren Diensten erforderlich ist. Das `Encoded`-Nachrichtenformat ist nur bei Verwendung von XmlSerializer verfügbar.

Damit Sie die gesendeten und empfangenen Nachrichten anzeigen können, basiert dieses Beispiel auf der Ablauf [Verfolgung und der Nachrichten Protokollierung](tracing-and-message-logging.md). Die Dienstkonfiguration und der Quellcode wurden geändert, um Ablaufverfolgung und Nachrichtenprotokollierung zu aktivieren und zu verwenden. Außerdem wurde <xref:System.ServiceModel.WSHttpBinding> ohne Sicherheit konfiguriert, sodass protokollierte Nachrichten in einem unverschlüsselten Format angezeigt werden können. Die resultierenden Ablauf Verfolgungs Protokolle (System. Service Model. e2e und Message. log) sollten mit dem [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)angezeigt werden. Die Ablaufverfolgungen sind so konfiguriert, dass sie im Ordner C:\LOGS erstellt werden. Erstellen Sie den Ordner vor dem Ausführen des Beispiels. Wenn Sie den Nachrichten Inhalt im Trace Viewer-Tool anzeigen möchten, wählen Sie im linken und rechten Bereich des Tools **Nachrichten** aus.

Im folgenden Code wird der Dienstvertrag veranschaulicht, wobei die <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A>-Eigenschaft auf <xref:System.ServiceModel.OperationFormatUse> festgelegt und das Format des Nachrichtentexts vom Standard (<xref:System.ServiceModel.OperationFormatStyle>) in <xref:System.ServiceModel.OperationFormatStyle.Document> geändert wurde.

```csharp
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

Um den Unterschied zwischen den unterschiedlichen Einstellungen für <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> und <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> zu verdeutlichen, ändern Sie sie im Dienst, generieren Sie den Client erneut, führen Sie das Beispiel aus, und betrachten Sie dann die Datei "c:\logs\message.logs" im Service Trace Viewer-Tool. Beachten Sie auch die Auswirkungen auf die Metadaten, indem Sie `http://localhost/ServiceModelSamples/service.svc?wsdl`anzeigen. Die Metadaten für Dienste sind normalerweise in mehrere Seiten untergeteilt. Die WSDL-Hauptseite enthält die WSDL-Bindungen, aber anzeigen `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0`, um die Nachrichten Definitionen zu beobachten.

## <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.

2. Erstellen Sie zum Protokollieren von Nachrichten das Verzeichnis C:\LOGS. Weisen Sie dem Benutzer Network Service die Schreibberechtigung für dieses Verzeichnis zu.

3. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.

4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.
> 
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`
