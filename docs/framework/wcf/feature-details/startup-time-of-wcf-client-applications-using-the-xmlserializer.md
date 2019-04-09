---
title: 'Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: dfc3dc8247a25442511d422192fea4f49bee5d92
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169805"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a>Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer
Dienste und Clientanwendungen, die Datentypen verwenden, die mit dem <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können, generieren und kompilieren für diese Datentypen während der Laufzeit Code, was zu einem verlangsamten Start führen kann.  
  
> [!NOTE]
>  Vorab generierter Serialisierungscode kann nur in Clientanwendungen verwendet werden und nicht in Diensten.  
  
 Die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) können startleistung für diese Anwendungen verbessern, indem der erforderliche Serialisierungscode aus den kompilierten Assemblys für die Anwendung generiert. Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können. Dienst- und Vorgangsverträge, die <xref:System.Xml.Serialization.XmlSerializer> verwenden, werden mit <xref:System.ServiceModel.XmlSerializerFormatAttribute> gekennzeichnet.  
  
### <a name="to-generate-xmlserializer-serialization-code"></a>So generieren Sie XmlSerializer-Serialisierungscode  
  
1.  Kompilieren Sie den Dienst- oder Clientcode in eine oder mehrere Assemblys.  
  
2.  Öffnen Sie eine SDK-Eingabeaufforderung.  
  
3.  Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format.  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     Das `assemblyPath`-Argument gibt den Pfad zu einer Assembly an, die Dienstvertragstypen enthält. Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.  
  
     Svcutil.exe kann lediglich C#-Serialisierungscode generieren. Für jede Eingabeassembly wird eine Quellcodedatei generiert. Sie können keine der **/Language** Switch so ändern Sie die Sprache des generierten Codes.  
  
     Um den Pfad für abhängige Assemblys anzugeben, verwenden die **/reference** Option.  
  
4.  Machen Sie den generierten Serialisierungscode für Ihre Anwendung verfügbar, indem Sie eine der folgenden Optionen verwenden:  
  
    1.  Kompilieren Sie den generierten Serialisierungscode in einer separaten Assembly mit dem Namen [*ursprüngliche Assembly*]. XmlSerializers.dll (z. B. MyApp.XmlSerializers.dll). Ihre Anwendung muss die Assembly laden können. Diese wiederum muss mit demselben Schlüssel wie die ursprüngliche Assembly signiert werden. Falls Sie die ursprüngliche Assembly neu kompilieren, müssen Sie die Serialisierungsassembly neu generieren.  
  
    2.  Kompilieren Sie den generierten Serialisierungscode in eine separate Assembly, und verwenden Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> in dem Dienstvertrag, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet. Legen Sie die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>-Eigenschaft oder die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>-Eigenschaft so fest, dass sie auf die kompilierte Serialisierungsassembly verweist.  
  
    3.  Kompilieren Sie den generierten Serialisierungscode in Ihre Anwendungsassembly, und fügen Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> dem Dienstvertrag hinzu, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet. Die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>-Eigenschaft und die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>-Eigenschaft müssen nicht festgelegt werden. Es wird davon ausgegangen, dass die Standardserialisierungsassembly die aktuelle Assembly ist.  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a>Zum Generieren von XmlSerializer-Serialisierungscode in Visual Studio  
  
1.  Erstellen Sie den WCF-Dienst und Client Projekte in Visual Studio. Anschließend fügen Sie einen Dienstverweis auf das Clientprojekt hinzu.  
  
2.  Hinzufügen einer <xref:System.ServiceModel.XmlSerializerFormatAttribute> auf den Dienstvertrag in der *reference.cs* -Datei in das Client-app-Projekt unter **ServiceReference** -> **"Reference.SVCMAP"** . Beachten Sie, dass Sie alle Dateien in anzeigen müssen **Projektmappen-Explorer** auf diese Dateien finden Sie unter.  
  
3.  Erstellen Sie die Client-app.  
  
4.  Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Erstellen einer vorab generierte Serialisierungsmodul *cs* Datei mithilfe des Befehls:  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     Das AssemblyPath-Argument gibt den Pfad zu die WCF-Clientassembly.  
  
     Z. B.:  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     Die *WCFClient.XmlSerializers.dll.cs* Datei generiert werden.  
  
5.  Kompilieren Sie die vorab generierte Serialisierungsassembly.  
  
     Basierend auf dem Beispiel im vorherigen Schritt, würde der Compile-Befehl kann Folgendes sein:  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     Stellen Sie sicher, dass die generierte *WCFClient.XmlSerializers.dll* befindet sich im gleichen Verzeichnis wie die Client-app, d.h. *WCFClient.exe* in diesem Fall.  
  
6.  Führen Sie die Client-app wie gewohnt. Der vorgenerierten Serialisierungsassembly wird verwendet.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl generiert Serialisierungstypen für `XmlSerializer`-Typen, die von Dienstverträgen in der Assembly verwendet werden.  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a>Siehe auch

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
