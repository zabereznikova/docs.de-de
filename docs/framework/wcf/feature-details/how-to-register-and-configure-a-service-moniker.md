---
title: 'Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: 2f8f19e70b3345b61f1f5caba2fc6f764b58cc9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54593796"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a>Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers
Vor der Verwendung des Windows Communication Foundation (WCF)-dienstmonikers in COM-Anwendung mit einem typisierten Vertrag, müssen Sie die erforderlichen attributierten Typen bei COM registriert werden, und konfigurieren die COM-Anwendung sowie der Moniker mit der erforderlichen Bindung die Konfiguration.  
  
### <a name="to-register-the-required-attributed-types-with-com"></a>So registrieren Sie die erforderlichen attributierten Typen bei COM  
  
1.  Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool, um den metadatenvertrag vom WCF-Dienst abrufen. Dadurch wird den Quellcode für eine WCF-Client-Assembly und eine clientanwendungs-Konfigurationsdatei generiert.  
  
2.  Stellen Sie sicher, dass die Typen in der Assembly als `ComVisible` markiert sind. Fügen Sie hierzu der Datei AssemblyInfo.cs in Ihrem Visual Studio-Projekt das folgende Attribut hinzu:  
  
    ```  
    [assembly: ComVisible(true)]  
    ```  
  
3.  Kompilieren Sie den verwalteten WCF-Client als eine Assembly mit starkem Namen. Dies erfordert die Signierung mit einem kryptografischen Schlüsselpaar. Weitere Informationen finden Sie unter [Signieren einer Assembly mit einem starken Namen](https://go.microsoft.com/fwlink/?LinkId=94874) im .NET Developer's Guide.  
  
4.  Verwenden Sie das Assemblyregistrierungstool (Regasm.exe) mit der `/tlb`-Option, um die Typen in der Assembly bei COM zu registrieren.  
  
5.  Fügen Sie die Assembly mithilfe des Tools für den globalen Assemblycache (Gacutil.exe) dem globalen Assemblycache hinzu.  
  
    > [!NOTE]
    >  Das Signieren sowie das Hinzufügen der Assembly zum globalen Assemblycache sind optionale Schritte, sie dienen jedoch zum Vereinfachen des Prozesses zum Laden der Assembly aus dem korrekten Speicherort im Laufzeitmodus.  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a>So konfigurieren Sie die COM-Anwendung und den Moniker mit der erforderlichen Bindungskonfiguration  
  
-   Platzieren Sie die Bindungsdefinitionen (von generiert die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in der Konfigurationsdatei der generierte Client-Anwendung) in der Konfigurationsdatei der Clientanwendung. Beispiel: Für eine ausführbare Visual Basic 6.0-Datei mit dem Namen CallCenterClient.exe muss die Konfiguration in eine Datei mit dem Namen CallCenterConfig.exe.config platziert werden, und diese Datei muss sich im gleichen Verzeichnis befinden wie die ausführbare Datei. Der Moniker kann nun von der Clientanwendung verwendet werden. Beachten Sie, die die Bindungskonfiguration nicht erforderlich, ist wenn eines der Bindung von WCF bereitgestellter Typen verwenden.  
  
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
    >  : Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar ist, wird der Aufruf von `GetObject` gibt die Fehlermeldung "Ungültige Syntax". Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
     Obgleich in diesem Thema hauptsächlich die Verwendung des Dienstmonikers in VB 6.0-Code behandelt wird, können Dienstmoniker auch in anderen Sprachen verwendet werden. Bei Verwendung eines Monikers in C++-Code muss die von Svcutil.exe generierte Assembly gemäß dem folgenden Beispiel mit "no_namespace named_guids raw_interfaces_only" importiert werden:  
  
    ```  
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     Dadurch wird die importierte Schnittstellendefinitionen geändert, sodass von allen Methoden `HResult` zurückgegeben wird. Alle anderen Rückgabewerte werden zu out-Parametern umgewandelt. An der Ausführung der Methoden ändert das nichts. Dies ermöglicht es Ihnen, beim Aufrufen einer Methode auf dem Proxy die Ursache einer Ausnahme zu bestimmen. Diese Funktion ist ausschließlich in C++-Code verfügbar.  
  
## <a name="see-also"></a>Siehe auch
- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
