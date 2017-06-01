---
title: "WCF Data Service-Clienthilfsprogramm (DataSvcUtil.exe) | Microsoft Docs"
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
  - "WCF Data Services, Verarbeiten"
  - "WCF Data Services, Erstellen von Clientdatenklassen"
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# WCF Data Service-Clienthilfsprogramm (DataSvcUtil.exe)
**DataSvcUtil.exe** ist ein von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] bereitgestelltes Befehlszeilentool, das einen [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-Feed verwendet und Clientdatendienstklassen generiert, die zum Zugriff auf einen Datendienst aus einer .NET Framework\-Clientanwendung benötigt werden.  Dieses Hilfsprogramm kann Datenklassen mit den folgenden Metadaten\-Quellen generieren:  
  
-   Der Stamm\-URI eines Datendiensts.  Das Dienstprogramm fordert das Dienstmetadatendokument an, in dem das vom Datendienst verfügbar gemachte Datenmodell beschrieben wird.  Weitere Informationen finden Sie unter [OData: Dienstmetadatendokument](http://go.microsoft.com/fwlink/?LinkId=186070).  
  
-   Eine mit der konzeptionellen Schemadefinitionssprache \(CSDL\) definierte Datenmodelldatei \(.csdl\), wie in der [\[MC\-CSDL\]: Conceptual Schema Definition File Format](http://go.microsoft.com/fwlink/?LinkID=159072)\-Spezifikation definiert.  
  
-   Eine mit den Entity Data Model\-Tools erstellte EDMX\-Datei, die mit Entity Framework bereitgestellt werden.  Weitere Informationen finden Sie in der Spezifikation [\[MC\-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833).  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Manuelles Generieren von Clientdatendienstklassen](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
 Das Tool DataSvcUtil.exe wird im [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Verzeichnis installiert.  Dieses befindet sich meist unter C:\\Windows\\Microsoft.NET\\Framework\\v4.0.  Bei 64\-Bit\-Systemen befindet es sich unter C:\\Windows\\Microsoft.NET\\Framework64\\v4.0.  Zusätzlich können Sie mithilfe der Eingabeaufforderung von Visual Studio auf das Tool **DataSvcUtil.exe** zugreifen. \(Klicken Sie auf **Start**, zeigen Sie auf **Programme**, **Microsoft Visual Studio 2010** und **Visual Studio Tools**, und klicken Sie dann auf **Visual Studio 2010\-Eingabeaufforderung**.\)  
  
## Syntax  
  
```  
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]  
```  
  
#### Parameter  
  
|Option|Beschreibung|  
|------------|------------------|  
|`/dataservicecollection`|Gibt an, dass der zum Binden von Objekten an Steuerelemente erforderliche Code auch generiert wird.|  
|`/help`<br /><br /> \- oder \-<br /><br /> `/?`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|`/in:` *\<file\>*|Gibt die CSDL\- oder EDMX\-Datei oder ein Verzeichnis an, in dem sich die Datei befindet.|  
|`/language:`\[VB&#124;CSharp\]|Gibt die Sprache für die erstellten Quellcodedateien an.  Die Standardsprache ist C\#.|  
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|  
|`/out:` *\<file\>*|Gibt den Namen der Quellcodedatei an, die die generierten Clientdatendienstklassen enthält.|  
|`/uri:` *\<string\>*|Der URI des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Feeds.|  
|`/version:`\[1.0&#124;2.0\]|Gibt die höchste akzeptierte Version von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] an.  Die Version wird auf Grundlage des `DataServiceVersion`\-Attributs des DataService\-Elements in den zurückgegebenen Datendienstmetadaten bestimmt.  Weitere Informationen finden Sie unter [Datendienst\-Versionskontrolle](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).  Wenn Sie den `/dataservicecollection`\-Parameter angeben, müssen Sie auch `/version:2.0` angeben, um die Datenbindung zu aktivieren.|  
  
## Siehe auch  
 [Generieren der Datendienst\-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)   
 [Gewusst wie: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)