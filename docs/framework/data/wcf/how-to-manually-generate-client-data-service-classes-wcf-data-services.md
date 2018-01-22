---
title: 'Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- WCF Data Services, client library
ms.assetid: b98cb1d6-956a-4e50-add6-67e4f2587346
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dba117ac9f4fd7dc745019d9705c2a707a5b526c
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-manually-generate-client-data-service-classes-wcf-data-services"></a>Gewusst wie: Manuelles Generieren von Client-Datendienstklassen (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]Aktivieren Sie zum automatischen Generieren von clientdatendienstklassen bei Verwendung von Visual Studio integriert die **Hinzufügen eines Dienstverweises** Dialogfeld in Visual Studio-Projekt einen Verweis auf einen Datendienst hinzu. Weitere Informationen finden Sie unter [wie: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md). Sie können auch die gleichen Clientdatendienstklassen mit dem Tool zur Codeerstellung `DataSvcUtil.exe` manuell generieren. Dieses Tool, das in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] enthalten ist, generiert aus der Datendienstdefinition .NET Framework-Klassen. Es kann auch verwendet werden, um Datendienstklassen aus der Konzeptmodelldatei (CSDL) und der EDMX-Datei zu generieren, die ein Entity Framework-Modell in einem Visual Studio-Projekt darstellt.  
  
 Im Beispiel in diesem Thema werden Clientdatendienstklassen basierend auf dem Northwind-Beispieldatendienst erstellt. Dieser Dienst wird erstellt, Sie nach Beendigung der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Für einige Beispiele in diesem Thema ist die Konzeptmodelldatei für das Northwind-Modell erforderlich. Weitere Informationen finden Sie unter [Vorgehensweise: verwenden EdmGen.exe generiert die Modell- und Zuordnen von Dateien](../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md). Für einige Beispiele in diesem Thema ist die EDMX-Datei für das Northwind-Modell erforderlich. Weitere Informationen finden Sie unter [EDMX-Datei (Übersicht)](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4).  
  
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
 [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [Vorgehensweise: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)  
 [WCF Data Service-Clienthilfsprogramm („DataSvcUtil.exe“)](../../../../docs/framework/data/wcf/wcf-data-service-client-utility-datasvcutil-exe.md)
