---
title: "POCO-Unterst&#252;tzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# POCO-Unterst&#252;tzung
In diesem Beispiel wird die Serialisierungsunterstützung für makellose Typen demonstriert, d. h. Typen, auf die Serialisierungsattribute nicht angewendet wurden \(diese werden auch als POCO\-Typen \(Plain Old CLR Object\) bezeichnet\).Der <xref:System.Runtime.Serialization.DataContractSerializer> leitet einen Datenvertrag für alle öffentlichen makellosen Typen ab, die über einen Standardkonstruktor verfügen.Datenverträge ermöglichen es Ihnen, strukturierte Daten an Dienste zu übergeben und von ihnen zu empfangen.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu nicht markierten Typen finden Sie unter [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
 Dieses Beispiel basiert auf dem [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md), es werden jedoch komplexe Zahlen anstelle primitiver numerischer Typen verwendet.Es ähnelt auch dem Beispiel [Grundlegender Datenvertrag](../../../../docs/framework/wcf/samples/basic-data-contract.md), außer dass das <xref:System.Runtime.Serialization.DataContractAttribute>\-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>\-Attribut nicht verwendet werden.  
  
 Der Dienst wird von Internetinformationsdiensten \(IIS\) gehostet, und der Client ist eine Konsolenanwendung \(.exe\).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Die `ComplexNumber`\-Klasse wird im `ServiceContract` verwendet.Der `ComplexNumber`\-Typ verfügt nicht über das <xref:System.Runtime.Serialization.DataContractAttribute>\-Attribut und das <xref:System.Runtime.Serialization.DataMemberAttribute>\-Attribut, wie im folgenden Beispielcode dargestellt.Standardmäßig werden alle öffentlichen Eigenschaften und Felder serialisiert.  
  
```  
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
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
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## Siehe auch  
 <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>   
 [Serialisierbare Typen](../../../../docs/framework/wcf/feature-details/serializable-types.md)