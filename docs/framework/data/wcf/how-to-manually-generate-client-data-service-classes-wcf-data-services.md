---
title: 'Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 31bf2e543bf20199fbeeaa8d00f808650092ff00
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546958"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)
WCF Data Services ist in Visual Studio integriert, damit Sie automatisch Client Datendienst Klassen generieren können, wenn Sie das Dialogfeld **Dienstverweis hinzufügen** verwenden, um einen Verweis auf einen Datendienst in einem Visual Studio-Projekt hinzuzufügen. Weitere Informationen finden Sie unter Vorgehens [Weise: Hinzufügen eines Datendienst Verweises](how-to-add-a-data-service-reference-wcf-data-services.md). Sie können auch die gleichen Clientdatendienstklassen mit dem Tool zur Codeerstellung `DataSvcUtil.exe` manuell generieren. Dieses Tool, das in WCF Data Services enthalten ist, generiert .NET Framework Klassen aus der Datendienst Definition. Es kann auch verwendet werden, um Datendienstklassen aus der Konzeptmodelldatei (CSDL) und der EDMX-Datei zu generieren, die ein Entity Framework-Modell in einem Visual Studio-Projekt darstellt.

 Im Beispiel in diesem Thema werden Clientdatendienstklassen basierend auf dem Northwind-Beispieldatendienst erstellt. Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen. Für einige Beispiele in diesem Thema ist die Konzeptmodelldatei für das Northwind-Modell erforderlich. Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von EdmGen.exe zum Generieren von Modell-und Mapping-Dateien](../adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md). Für einige Beispiele in diesem Thema ist die EDMX-Datei für das Northwind-Modell erforderlich. Weitere Informationen finden Sie unter [Übersicht über die EDMX-Datei](/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).

### <a name="to-generate-c-classes-that-support-data-binding"></a>So erstellen Sie C#-Klassen, die die Datenbindung unterstützen

- Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>So erstellen Sie Visual Basic-Klassen, die die Datenbindung unterstützen

- Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.

### <a name="to-generate-c-classes-based-on-the-service-uri"></a>So erstellen Sie C#-Klassen basierend auf dem Dienst-URI

- Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>So erstellen Sie Visual Basic-Klassen basierend auf dem Dienst-URI

- Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    > Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>So erstellen Sie C#-Klassen basierend auf der Konzeptmodelldatei (CSDL)

- Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>So erstellen Sie Visual Basic-Klassen basierend auf der Konzeptmodelldatei (CSDL)

- Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>So erstellen Sie C#-Klassen basierend auf der EDMX-Datei

- Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>So erstellen Sie Visual Basic-Klassen basierend auf der EDMX-Datei

- Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```console
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a>Siehe auch

- [Generieren der Datendienstclientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)
- [Vorgehensweise: Hinzufügen eines Datendienstverweises](how-to-add-a-data-service-reference-wcf-data-services.md)
- [WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")](wcf-data-service-client-utility-datasvcutil-exe.md)
