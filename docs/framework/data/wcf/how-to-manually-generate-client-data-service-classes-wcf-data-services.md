---
title: 'Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
ms.openlocfilehash: 332c04f50e104a5e1c8bd18c05581b6c0472f82f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43501320"
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)
WCF Data Services-Integration mit Visual Studio können Sie Client-Datendienstklassen automatisch zu generieren, bei der Verwendung der **Hinzufügen eines Dienstverweises** einen Verweis auf einen Datendienst in einem Visual Studio-Projekt hinzufügen. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md). Sie können auch die gleichen Clientdatendienstklassen mit dem Tool zur Codeerstellung `DataSvcUtil.exe` manuell generieren. Dieses Tool, das in WCF Data Services enthalten ist, generiert .NET Framework-Klassen aus der Datendienstdefinition. Es kann auch verwendet werden, um Datendienstklassen aus der Konzeptmodelldatei (CSDL) und der EDMX-Datei zu generieren, die ein Entity Framework-Modell in einem Visual Studio-Projekt darstellt.

 Im Beispiel in diesem Thema werden Clientdatendienstklassen basierend auf dem Northwind-Beispieldatendienst erstellt. Dieser Dienst wird erstellt, Sie nach Beendigung der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Für einige Beispiele in diesem Thema ist die Konzeptmodelldatei für das Northwind-Modell erforderlich. Weitere Informationen finden Sie unter [wie: Generieren Sie das Modell und die Mapping-Dateien mithilfe von EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md). Für einige Beispiele in diesem Thema ist die EDMX-Datei für das Northwind-Modell erforderlich. Weitere Informationen finden Sie unter [EDMX-Datei Übersicht](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).

### <a name="to-generate-c-classes-that-support-data-binding"></a>So erstellen Sie C#-Klassen, die die Datenbindung unterstützen

-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.

### <a name="to-generate-visual-basic-classes-that-support-data-binding"></a>So erstellen Sie Visual Basic-Klassen, die die Datenbindung unterstützen

-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.

### <a name="to-generate-c-classes-based-on-the-service-uri"></a>So erstellen Sie C#-Klassen basierend auf dem Dienst-URI

-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.

### <a name="to-generate-visual-basic-classes-based-on-the-service-uri"></a>So erstellen Sie Visual Basic-Klassen basierend auf dem Dienst-URI

-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc
    ```

    > [!NOTE]
    >  Sie müssen den für den `/uri:`-Parameter angegebenen Wert durch den URI der Instanz des Northwind-Beispieldatendiensts ersetzen.

### <a name="to-generate-c-classes-based-on-the-conceptual-model-file-csdl"></a>So erstellen Sie C#-Klassen basierend auf der Konzeptmodelldatei (CSDL)

-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-conceptual-model-file-csdl"></a>So erstellen Sie Visual Basic-Klassen basierend auf der Konzeptmodelldatei (CSDL)

-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb
    ```

### <a name="to-generate-c-classes-based-on-the-edmx-file"></a>So erstellen Sie C#-Klassen basierend auf der EDMX-Datei

-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs
    ```

### <a name="to-generate-visual-basic-classes-based-on-the-edmx-file"></a>So erstellen Sie Visual Basic-Klassen basierend auf der EDMX-Datei

-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:

    ```
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb
    ```

## <a name="see-also"></a>Siehe auch

- [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [Vorgehensweise: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
- [WCF Data Service-Clienthilfsprogramm („DataSvcUtil.exe“)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)