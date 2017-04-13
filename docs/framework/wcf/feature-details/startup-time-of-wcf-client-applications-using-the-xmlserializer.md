---
title: "Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer
Dienste und Clientanwendungen, die Datentypen verwenden, die mit dem <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können, generieren und kompilieren für diese Datentypen während der Laufzeit Code, was zu einem verlangsamten Start führen kann.  
  
> [!NOTE]
>  Vorab generierter Serialisierungscode kann nur in Clientanwendungen und nicht in Diensten verwendet werden.  
  
 Das [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) kann die Startleistung für diese Anwendungen verbessern, indem der erforderliche Serialisierungscode aus den kompilierten Assemblys für die Anwendung generiert wird.Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.Dienst\- und Vorgangsverträge, die <xref:System.Xml.Serialization.XmlSerializer> verwenden, werden mit <xref:System.ServiceModel.XmlSerializerFormatAttribute> gekennzeichnet.  
  
### So generieren Sie XmlSerializer\-Serialisierungscode  
  
1.  Kompilieren Sie den Dienst\- oder Clientcode in eine oder mehrere Assemblys.  
  
2.  Öffnen Sie eine SDK\-Eingabeaufforderung.  
  
3.  Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format.  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     Das `assemblyPath`\-Argument gibt den Pfad zu einer Assembly an, die Dienstvertragstypen enthält.Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.  
  
     Svcutil.exe kann lediglich C\#\-Serialisierungscode generieren.Für jede Eingabeassembly wird eine Quellcodedatei generiert.Sie können den Schalter **\/language** nicht verwenden, um die Sprache des generierten Codes zu ändern.  
  
     Den Pfad für abhängige Assemblys geben Sie mit der Option **\/reference** an.  
  
4.  Machen Sie den generierten Serialisierungscode für Ihre Anwendung verfügbar, indem Sie eine der folgenden Optionen verwenden:  
  
    1.  Kompilieren Sie den generierten Serialisierungscode in einer separaten Assembly mit der Bezeichnung \[*original assembly*\].XmlSerializers.dll \(z. B. MyApp.XmlSerializers.dll\).Ihre Anwendung muss die Assembly laden können. Diese wiederum muss mit demselben Schlüssel wie die ursprüngliche Assembly signiert werden.Falls Sie die ursprüngliche Assembly neu kompilieren, müssen Sie die Serialisierungsassembly neu generieren.  
  
    2.  Kompilieren Sie den generierten Serialisierungscode in eine separate Assembly, und verwenden Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> in dem Dienstvertrag, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet.Legen Sie die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>\-Eigenschaft oder die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>\-Eigenschaft so fest, dass sie auf die kompilierte Serialisierungsassembly verweist.  
  
    3.  Kompilieren Sie den generierten Serialisierungscode in Ihre Anwendungsassembly, und fügen Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> dem Dienstvertrag hinzu, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet.Die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>\-Eigenschaft und die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>\-Eigenschaft müssen nicht festgelegt werden.Es wird davon ausgegangen, dass die Standardserialisierungsassembly die aktuelle Assembly ist.  
  
## Beispiel  
 Der folgende Befehl generiert Serialisierungstypen für `XmlSerializer`\-Typen, die von Dienstverträgen in der Assembly verwendet werden.  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## Siehe auch  
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)