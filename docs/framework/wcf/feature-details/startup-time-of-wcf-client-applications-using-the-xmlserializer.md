---
title: 'Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer'
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: 91712963908ecc56ff17fbac028389207544b82f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600256"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a>Vorgehensweise: Verbessern der Startzeit von WCF-Clientanwendungen mit dem XmlSerializer
Dienste und Clientanwendungen, die Datentypen verwenden, die mit dem <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können, generieren und kompilieren für diese Datentypen während der Laufzeit Code, was zu einem verlangsamten Start führen kann.  
  
> [!NOTE]
> Vorab generierter Serialisierungscode kann nur in Clientanwendungen verwendet werden und nicht in Diensten.  
  
 Das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) kann die Startleistung für diese Anwendungen verbessern, indem der erforderliche Serialisierungscode aus den kompilierten Assemblys für die Anwendung erzeugt wird. Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können. Dienst- und Vorgangsverträge, die <xref:System.Xml.Serialization.XmlSerializer> verwenden, werden mit <xref:System.ServiceModel.XmlSerializerFormatAttribute> gekennzeichnet.  
  
### <a name="to-generate-xmlserializer-serialization-code"></a>So generieren Sie XmlSerializer-Serialisierungscode  
  
1. Kompilieren Sie den Dienst- oder Clientcode in eine oder mehrere Assemblys.  
  
2. Öffnen Sie eine SDK-Eingabeaufforderung.  
  
3. Starten Sie das Tool Svcutil.exe an der Eingabeaufforderung mit dem folgenden Format.  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     Das `assemblyPath`-Argument gibt den Pfad zu einer Assembly an, die Dienstvertragstypen enthält. Svcutil.exe generiert Serialisierungscode für alle Datentypen, die in Dienstverträgen in der kompilierten Anwendungsassembly verwendet werden und die mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden können.  
  
     Svcutil.exe kann lediglich C#-Serialisierungscode generieren. Für jede Eingabeassembly wird eine Quellcodedatei generiert. Sie können den Schalter **/Language** nicht verwenden, um die Sprache des generierten Codes zu ändern.  
  
     Verwenden Sie die **/Reference** -Option, um den Pfad zu abhängigen Assemblys anzugeben.  
  
4. Machen Sie den generierten Serialisierungscode für Ihre Anwendung verfügbar, indem Sie eine der folgenden Optionen verwenden:  
  
    1. Kompilieren Sie den generierten Serialisierungscode in eine separate Assembly mit dem Namen [*ursprüngliche Assembly*]. Xmlserializers. dll (z. b. MyApp. xmlserializers. dll). Ihre Anwendung muss die Assembly laden können. Diese wiederum muss mit demselben Schlüssel wie die ursprüngliche Assembly signiert werden. Falls Sie die ursprüngliche Assembly neu kompilieren, müssen Sie die Serialisierungsassembly neu generieren.  
  
    2. Kompilieren Sie den generierten Serialisierungscode in eine separate Assembly, und verwenden Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> in dem Dienstvertrag, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet. Legen Sie die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>-Eigenschaft oder die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>-Eigenschaft so fest, dass sie auf die kompilierte Serialisierungsassembly verweist.  
  
    3. Kompilieren Sie den generierten Serialisierungscode in Ihre Anwendungsassembly, und fügen Sie <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> dem Dienstvertrag hinzu, der <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet. Die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A>-Eigenschaft und die <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A>-Eigenschaft müssen nicht festgelegt werden. Es wird davon ausgegangen, dass die Standardserialisierungsassembly die aktuelle Assembly ist.  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a>So generieren Sie XmlSerializer-Serialisierungscode in Visual Studio  
  
1. Erstellen Sie den WCF-Dienst und die Client Projekte in Visual Studio. Fügen Sie dann dem Client Projekt einen Dienst Verweis hinzu.  
  
2. Fügen Sie <xref:System.ServiceModel.XmlSerializerFormatAttribute> dem Dienstvertrag in der *Reference.cs* -Datei im Client-App-Projekt unter **servicereferenzierungsreferenz**  ->  **. svcmap**einen hinzu. Beachten Sie, dass Sie alle Dateien in **Projektmappen-Explorer** anzeigen müssen, um diese Dateien anzuzeigen.  
  
3. Erstellen Sie die Client-App.  
  
4. Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um mithilfe des Befehls eine vorab generierte Datei Serialisierungsprogramm *. cs* zu erstellen:  
  
    ```console  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     Das assemblyPath-Argument gibt den Pfad zur WCF-Clientassembly an.  
  
     Also beispielsweise:  
  
    ```console  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     Die *wcfClient.xmlserializers.dll.cs* -Datei wird generiert.  
  
5. Kompilieren Sie die vorgenerierte Serialisierungsassembly.  
  
     Basierend auf dem Beispiel im vorherigen Schritt würde der Kompilierungs Befehl folgendermaßen lauten:  
  
    ```console  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     Stellen Sie sicher, dass sich die generierte Datei " *wcfClient. xmlserializers. dll* " im gleichen Verzeichnis wie die Client-App befindet, in diesem Fall " *wcfClient. exe* ".  
  
6. Führen Sie die Client-App wie gewohnt aus. Die vorgenerierte Serialisierungsassembly wird verwendet.  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl generiert Serialisierungstypen für `XmlSerializer`-Typen, die von Dienstverträgen in der Assembly verwendet werden.  
  
```console  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
