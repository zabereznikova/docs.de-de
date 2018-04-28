---
title: 'Gewusst wie: Registrieren und Konfigurieren eines Dienstmonikers'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 52b3ec27560ca2dc47b7951cb209f33f307fa7ea
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-register-and-configure-a-service-moniker"></a>Gewusst wie: Registrieren und Konfigurieren eines Dienstmonikers
Vor der Verwendung eines [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienstmonikers in einer COM-Anwendung mit einem typisierten Vertrag müssen die erforderlichen attributierten Typen bei COM registriert werden. Des Weiteren müssen die COM-Anwendung sowie der Moniker mit der erforderlichen Bindungskonfiguration konfiguriert werden.  
  
### <a name="to-register-the-required-attributed-types-with-com"></a>So registrieren Sie die erforderlichen attributierten Typen bei COM  
  
1.  Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool zum Abrufen des Metadaten-Vertrags aus der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst. Dadurch werden der Quellcode für eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly sowie eine Konfigurationsdatei für die Clientanwendung generiert.  
  
2.  Stellen Sie sicher, dass die Typen in der Assembly als `ComVisible` markiert sind. Fügen Sie hierzu der Datei AssemblyInfo.cs in Ihrem Visual Studio-Projekt das folgende Attribut hinzu:  
  
    ```  
    [assembly: ComVisible(true)]  
    ```  
  
3.  Kompilieren Sie den verwalteten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client als Assembly mit starkem Namen. Dies erfordert die Signierung mit einem kryptografischen Schlüsselpaar. Weitere Informationen finden Sie unter [Signieren einer Assembly mit einem starken Namen](http://go.microsoft.com/fwlink/?LinkId=94874) in .NET Developer's Guide.  
  
4.  Verwenden Sie das Assemblyregistrierungstool (Regasm.exe) mit der `/tlb`-Option, um die Typen in der Assembly bei COM zu registrieren.  
  
5.  Fügen Sie die Assembly mithilfe des Tools für den globalen Assemblycache (Gacutil.exe) dem globalen Assemblycache hinzu.  
  
    > [!NOTE]
    >  Das Signieren sowie das Hinzufügen der Assembly zum globalen Assemblycache sind optionale Schritte, sie dienen jedoch zum Vereinfachen des Prozesses zum Laden der Assembly aus dem korrekten Speicherort im Laufzeitmodus.  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a>So konfigurieren Sie die COM-Anwendung und den Moniker mit der erforderlichen Bindungskonfiguration  
  
-   Platzieren Sie die Bindungsdefinitionen (generiert durch die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in der Konfigurationsdatei der generierte Client-Anwendung) in der Konfigurationsdatei der Clientanwendung. Beispiel: Für eine ausführbare Visual Basic 6.0-Datei mit dem Namen CallCenterClient.exe muss die Konfiguration in eine Datei mit dem Namen CallCenterConfig.exe.config platziert werden, und diese Datei muss sich im gleichen Verzeichnis befinden wie die ausführbare Datei. Der Moniker kann nun von der Clientanwendung verwendet werden. Hinweis: Die Bindungskonfiguration ist nicht erforderlich, wenn einer der von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bereitgestellten Standardbindungstypen verwendet wird.  
  
     Der folgende Typ wird registriert:  
  
    ```  
    using System.ServiceModel;  
  
    ...  
  
    [ServiceContract]   
    public interface IMathService   
    {  
    [OperationContract]  
    public int Add(int x, int y);  
    [OperationContract]  
    public int Subtract(int x, int y);  
    }  
    ```  
  
     Die Anwendung wird mit einer `wsHttpBinding`-Bindung verfügbar gemacht. Für den angegebenen Typ und die Anwendungskonfiguration werden die folgenden Beispielmonikerzeichenfolgen verwendet:  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
    ```  
  
     `or`  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
    ```  
  
     Nachdem ein Verweis auf die Assembly mit den `IMathService`-Typen hinzugefügt wurde (siehe folgendes Codebeispiel), kann jede dieser Monikerzeichenfolgen in einer Visual Basic 6.0-Anwendung verwendet werden.  
  
    ```  
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
    ```  
  
     In diesem Beispiel wird die Definition für die Bindungskonfiguration `Binding1` in einer Konfigurationsdatei für die Clientanwendung mit geeignetem Namen (wie vb6appname.exe.config) gespeichert.  
  
    > [!NOTE]
    >  Für C#-, C++- oder andere .NET-Anwendung kann ein ähnlicher Code verwendet werden.  
  
    > [!NOTE]
    >  : Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben. Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
     Obgleich in diesem Thema hauptsächlich die Verwendung des Dienstmonikers in VB 6.0-Code behandelt wird, können Dienstmoniker auch in anderen Sprachen verwendet werden. Bei Verwendung eines Monikers in C++-Code muss die von Svcutil.exe generierte Assembly gemäß dem folgenden Beispiel mit "no_namespace named_guids raw_interfaces_only" importiert werden:  
  
    ```  
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     Dadurch wird die importierte Schnittstellendefinitionen geändert, sodass von allen Methoden `HResult` zurückgegeben wird. Alle anderen Rückgabewerte werden zu out-Parametern umgewandelt. An der Ausführung der Methoden ändert das nichts. Dies ermöglicht es Ihnen, beim Aufrufen einer Methode auf dem Proxy die Ursache einer Ausnahme zu bestimmen. Diese Funktion ist ausschließlich in C++-Code verfügbar.  
  
## <a name="see-also"></a>Siehe auch  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
