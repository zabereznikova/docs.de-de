---
title: "Gewusst wie: Manuelles Generieren von Clientdatendienstklassen (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Clientbibliothek"
  - "WCF Data Services, Konfigurieren"
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Gewusst wie: Manuelles Generieren von Clientdatendienstklassen (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ist in Visual Studio integriert, um Ihnen das automatische Generieren von Clientdatendienstklassen zu ermöglichen, wenn Sie mithilfe des Dialogfelds **Dienstverweis hinzufügen** einem Datendienst in einem Visual Studio\-Projekt einen Verweis hinzuzufügen.  Weitere Informationen finden Sie unter [Gewusst wie: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  Sie können die gleichen Clientdatendienstklassen auch manuell mit dem Tool zur Codeerstellung `DataSvcUtil.exe` generieren. Dieses Tool, das in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enthalten ist, generiert .NET Framework\-Klassen aus der Datendienstdefinition.  Es kann auch verwendet werden, um Datendienstklassen aus der Konzeptmodelldatei \(CSDL\) und der EDMX\-Datei zu generieren, die ein Entity Framework\-Modell in einem Visual Studio\-Projekt darstellt.  
  
 Im Beispiel in diesem Thema werden Clientdatendienstklassen basierend auf dem Northwind\-Beispieldatendienst erstellt.  Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  Für einige Beispiele in diesem Thema ist die Konzeptmodelldatei für das Northwind\-Modell erforderlich.  Weitere Informationen finden Sie unter [Vorgehensweise: Generieren von Modell\- und Zuordnungsdateien mithilfe von EdmGen.exe](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  Für einige Beispiele in diesem Thema ist die EDMX\-Datei für das Northwind\-Modell erforderlich.  Weitere Informationen finden Sie unter [.edmx File Overview](http://msdn.microsoft.com/de-de/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  
  
### So erstellen Sie C\#\-Klassen, die die Datenbindung unterstützen  
  
-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:CSharp /out:Northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Sie müssen den für den `/uri:`\-Parameter angegebenen Wert durch den URI der Instanz des Northwind\-Beispieldatendiensts ersetzen.  
  
### So erstellen Sie Visual Basic\-Klassen, die die Datenbindung unterstützen  
  
-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /dataservicecollection /version:2.0 /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Sie müssen den für den `/uri:`\-Parameter angegebenen Wert durch den URI der Instanz des Northwind\-Beispieldatendiensts ersetzen.  
  
### So erstellen Sie C\#\-Klassen basierend auf dem Dienst\-URI  
  
-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\DataSvcUtil.exe" /language:CSharp /out:northwind.cs /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Sie müssen den für den `/uri:`\-Parameter angegebenen Wert durch den URI der Instanz des Northwind\-Beispieldatendiensts ersetzen.  
  
### So erstellen Sie Visual Basic\-Klassen basierend auf dem Dienst\-URI  
  
-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /out:Northwind.vb /uri:http://localhost:12345/Northwind.svc  
    ```  
  
    > [!NOTE]
    >  Sie müssen den für den `/uri:`\-Parameter angegebenen Wert durch den URI der Instanz des Northwind\-Beispieldatendiensts ersetzen.  
  
### So erstellen Sie C\#\-Klassen basierend auf der Konzeptmodelldatei \(CSDL\)  
  
-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.csdl /out:Northwind.cs  
    ```  
  
### So erstellen Sie Visual Basic\-Klassen basierend auf der Konzeptmodelldatei \(CSDL\)  
  
-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.csdl /out:Northwind.vb  
    ```  
  
### So erstellen Sie C\#\-Klassen basierend auf der EDMX\-Datei  
  
-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:CSharp /in:Northwind.edmx /out:c:\northwind.cs   
    ```  
  
### So erstellen Sie Visual Basic\-Klassen basierend auf der EDMX\-Datei  
  
-   Führen Sie an der Eingabeaufforderung den folgenden Befehl ohne Zeilenumbrüche aus:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v3.5\datasvcutil.exe" /language:VB /in:Northwind.edmx /out:c:\northwind.vb   
    ```  
  
## Siehe auch  
 [Generieren der Datendienst\-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)   
 [Gewusst wie: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)   
 [WCF Data Service\-Clienthilfsprogramm \(DataSvcUtil.exe\)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)