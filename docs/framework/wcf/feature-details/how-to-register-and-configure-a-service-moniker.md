---
title: 'Gewusst wie: Registrieren und Konfigurieren eines Dienstmonikers'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
ms.openlocfilehash: fc0b2d00bcc8e3b14c491446f16297c1036b783b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747091"
---
# <a name="how-to-register-and-configure-a-service-moniker"></a>Gewusst wie: Registrieren und Konfigurieren eines Dienstmonikers

Vor der Verwendung des Windows Communication Foundation (WCF)-Dienstmonikers in einer COM-Anwendung mit einem typisierten Vertrag müssen Sie die erforderlichen attributierten Typen bei com registrieren und die COM-Anwendung und den Moniker mit der erforderlichen Bindung konfigurieren. konfiguri.

## <a name="register-the-required-attributed-types-with-com"></a>Registrieren der erforderlichen attributierten Typen bei com

1. Verwenden Sie das Tool [Service Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um den Metadatenvertrag aus dem WCF-Dienst abzurufen. Dadurch wird der Quellcode für eine WCF-Clientassembly und eine Client Anwendungs Konfigurationsdatei generiert.

2. Stellen Sie sicher, dass die Typen in der Assembly als `ComVisible` markiert sind. Fügen Sie zu diesem Zweck der Datei *AssemblyInfo.cs* in Ihrem Visual Studio-Projekt das folgende Attribut hinzu.

    ```csharp
    [assembly: ComVisible(true)]
    ```

3. Kompilieren Sie den verwalteten WCF-Client als Assembly mit starkem Namen. Dies erfordert die Signierung mit einem kryptografischen Schlüsselpaar. Weitere Informationen dazu finden Sie unter [Signing an Assembly with a Strong Name (Signieren einer Assembly mit starkem Namen)](../../../standard/assembly/sign-strong-name.md).

4. Verwenden Sie das Assemblyregistrierungstool (Regasm.exe) mit der `-tlb`-Option, um die Typen in der Assembly bei COM zu registrieren.

5. Fügen Sie die Assembly mithilfe des Tools für den globalen Assemblycache (Gacutil.exe) dem globalen Assemblycache hinzu.

    > [!NOTE]
    > Das Signieren sowie das Hinzufügen der Assembly zum globalen Assemblycache sind optionale Schritte, sie dienen jedoch zum Vereinfachen des Prozesses zum Laden der Assembly aus dem korrekten Speicherort im Laufzeitmodus.

## <a name="configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a>Konfigurieren Sie die COM-Anwendung und den Moniker mit der erforderlichen Bindungs Konfiguration.

- Platzieren Sie die Bindungs Definitionen (generiert durch das [Service Model Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) in der generierten Client Anwendungs Konfigurationsdatei) in der Konfigurationsdatei der Client Anwendung. Beispiel: Für eine ausführbare Visual Basic 6.0-Datei mit dem Namen CallCenterClient.exe muss die Konfiguration in eine Datei mit dem Namen CallCenterConfig.exe.config platziert werden, und diese Datei muss sich im gleichen Verzeichnis befinden wie die ausführbare Datei. Der Moniker kann nun von der Clientanwendung verwendet werden. Beachten Sie, dass die Bindungs Konfiguration nicht erforderlich ist, wenn Sie einen der Standard Bindungs Typen verwenden, die von WCF bereitgestellt werden.

     Der folgende Typ wird registriert:

    ```csharp
    using System.ServiceModel;

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

     oder

    ```
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}
    ```

     Nachdem ein Verweis auf die Assembly mit den `IMathService`-Typen hinzugefügt wurde (siehe folgendes Codebeispiel), kann jede dieser Monikerzeichenfolgen in einer Visual Basic 6.0-Anwendung verwendet werden.

    ```vb
    Dim mathProxy As IMathService
    Dim result As Integer

    Set mathProxy = GetObject( _
            "service4:address=http://localhost/MathService, _
            binding=wsHttpBinding, _
            bindingConfiguration=Binding1")

    result = mathProxy.Add(3, 5)
    ```

     In diesem Beispiel wird die Definition für die Bindungs Konfigurations `Binding1` in einer entsprechend benannten Konfigurationsdatei für die Client Anwendung gespeichert, z. b *. vb6appname. exe. config*.

    > [!NOTE]
    > Für C#-, C++- oder andere .NET-Anwendung kann ein ähnlicher Code verwendet werden.

    > [!NOTE]
    > Wenn der Moniker falsch formatiert ist oder der Dienst nicht verfügbar ist, gibt der Aufruf von `GetObject` den Fehler "Ungültige Syntax" zurück. Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.

     In diesem Thema liegt der Schwerpunkt auf der Verwendung des Dienstmonikers aus Visual Basic 6,0-Code, aber Sie können einen Dienstmoniker aus anderen Sprachen verwenden. Bei Verwendung eines Monikers in C++-Code muss die von Svcutil.exe generierte Assembly gemäß dem folgenden Beispiel mit "no_namespace named_guids raw_interfaces_only" importiert werden:

    ```cpp
    #import "ComTestProxy.tlb" no_namespace named_guids
    ```

     Dadurch wird die importierte Schnittstellendefinitionen geändert, sodass von allen Methoden `HResult` zurückgegeben wird. Alle anderen Rückgabewerte werden zu out-Parametern umgewandelt. An der Ausführung der Methoden ändert das nichts. Dies ermöglicht es Ihnen, beim Aufrufen einer Methode auf dem Proxy die Ursache einer Ausnahme zu bestimmen. Diese Funktion ist ausschließlich in C++-Code verfügbar.

## <a name="see-also"></a>Weitere Informationen

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
