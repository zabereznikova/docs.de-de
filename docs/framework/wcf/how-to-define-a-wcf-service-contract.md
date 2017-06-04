---
title: "Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags | Microsoft Docs"
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
helpviewer_keywords: 
  - "Dienstverträge [WCF], Definieren"
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: 58
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 58
---
# Gewusst wie: Definieren eines Windows Communication Foundation-Dienstvertrags
Dies ist die erste von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] Anwendung erforderlich sind.Eine Übersicht über alle sechs Aufgaben finden Sie im Thema [Lernprogramm 'Erste Schritte'](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 Beim Erstellen eines grundlegenden [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Diensts besteht die erste Aufgabe im Definieren eines Dienstvertrags.Der Dienstvertrag gibt an, welche Vorgänge der Dienst unterstützt.Ein Vorgang ähnelt einer Webdienstmethode.Verträge werden durch Definieren einer C\+\+\-, einer C\#\- oder einer Visual Basic \(VB\)\-Schnittstelle erstellt.Jede Methode in der Schnittstelle entspricht einem bestimmten Dienstvorgang.Auf jede Schnittstelle muss das <xref:System.ServiceModel.ServiceContractAttribute> angewendet werden, und auf jeden Vorgang muss das <xref:System.ServiceModel.OperationContractAttribute>\-Attribut angewendet werden.Besitzt eine Methode innerhalb einer Schnittstelle, die über das <xref:System.ServiceModel.ServiceContractAttribute>\-Attribut verfügt, nicht das <xref:System.ServiceModel.OperationContractAttribute>\-Attribut, wird diese Methode vom Dienst nicht verfügbar gemacht.  
  
 Der für diese Aufgabe verwendete Code wird in dem Beispiel im Anschluss an das Verfahren bereitgestellt.  
  
### So definieren Sie einen Dienstvertrag  
  
1.  Öffnen Sie [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] als Administrator, indem Sie im Menü **Start** mit der rechten Maustaste auf das Programm klicken und **Als Administrator ausführen** auswählen.  
  
2.  Erstellen Sie ein WCF\-Dienstbibliotheksprojekt, indem Sie im Menü **Datei** auf **Neu** klicken und anschließend **Projekt** auswählen.Erweitern Sie im Dialogfeld **Neues Projekt** auf der linken Seite des Dialogfelds **Visual C\#** für ein C\#\-Projekt, oder klicken Sie auf **Andere Sprachen** und dann auf **Visual Basic** für ein Visual Basic\-Projekt.Wählen Sie unter der ausgewählten Sprache **WCF** aus. Eine Liste der Projektvorlagen wird im mittleren Abschnitt des Dialogfelds angezeigt.Wählen Sie **WCF\-Dienstbibliothek**, und geben Sie `GettingStartedLib` in das Textfeld **Name** und `GettingStarted` in das Textfeld **Projektmappenname** unten im Dialogfeld ein.  
  
3.  Visual Studio erstellt das Projekt, das 3 Dateien enthält: IService1.vb oder IService1.cs \(\) \(Service1.cs oder Service1.vb\) und App.config.Die Datei IService1 enthält einen standardmäßigen Dienstvertrag.Die Datei Service1 enthält eine Standardimplementierung des Dienstvertrags.Die Datei App.config enthält die Konfiguration, die erforderlich ist, um den Standarddienst mit dem Visual Studio\-WCF\-Diensthost zu laden.Weitere Informationen zum WCF\-Diensthost\-Tool finden Sie unter [WCF\-Diensthost \(WcfSvcHost.exe\)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
4.  Öffnen Sie die Datei IService1.cs oder IService1.vb, und löschen Sie den Code in der Namespacedeklaration, wobei Sie die Namespacedeklaration beibehalten.Innerhalb der Namespacedeklaration definieren Sie eine neue Schnittstelle mit dem Namen `ICalculator` wie im Code unten dargestellt.  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
    namespace GettingStartedLib  
    {  
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
            public interface ICalculator  
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
    }  
  
    ```  
  
    ```  
    ‘IService.vb  
    Imports System  
    Imports System.ServiceModel  
  
    Namespace GettingStartedLib  
  
        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _  
        Public Interface ICalculator  
  
            <OperationContract()> _  
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double  
            <OperationContract()> _  
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double  
        End Interface  
    End Namespace  
  
    ```  
  
     Dieser Vertrag definiert eine Onlinerechner.Beachten Sie, dass die `ICalculator`\-Schnittstelle mit dem <xref:System.ServiceModel.ServiceContractAttribute>\-Attribut markiert ist.Dieses Attribut definiert einen Namespace, der verwendet wird, um den Vertragsnamen zu unterscheiden.Jeder Rechnervorgang wird mit dem <xref:System.ServiceModel.OperationContractAttribute>\-Attribut markiert.  
  
    > [!NOTE]
    >  Wird eine Schnittstelle, ein Member oder eine Klasse mithilfe von Attributen mit Anmerkungen versehen, können Sie im Namen des Attributs auf das "Attribute" verzichten.Deshalb wird <xref:System.ServiceModel.ServiceContractAttribute> in C\# zu `[ServiceContract]` oder in Visual Basic zu `<ServiceContract>`.  
  
## Siehe auch  
 <xref:System.ServiceModel.ServiceContractAttribute>   
 <xref:System.ServiceModel.OperationContractAttribute>   
 [Gewusst wie: Implementieren eines WCF\-Dienstvertrags](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)   
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)