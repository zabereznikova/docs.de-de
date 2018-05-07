---
title: WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 3206947d06a1736116674b70e469c20f8f4fca86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")
DataSvcUtil.exe ist ein Befehlszeilentool, das von bereitgestellten [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] nutzt, die eine [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed und generiert die Client-Datendienstklassen, die erforderlich sind, um von einer .NET Framework-Clientanwendung einen Datendienst zugreift. Dieses Hilfsprogramm kann Datenklassen mit den folgenden Metadaten-Quellen generieren:  
  
-   Der Stamm-URI eines Datendiensts. Das Dienstprogramm fordert das Dienstmetadatendokument an, in dem das vom Datendienst verfügbar gemachte Datenmodell beschrieben wird. Weitere Informationen finden Sie unter [OData: Dienstmetadatendokument](http://go.microsoft.com/fwlink/?LinkId=186070).  
  
-   Einer Datenmodelldatei (.csdl) mithilfe der konzeptionellen Schemadefinitionssprache (CSDL) definiert wird, gemäß der [ \[MC-CSDL\]: Conceptual Schema Definition File Format](http://go.microsoft.com/fwlink/?LinkID=159072) Spezifikation.  
  
-   Eine mit den Entity Data Model-Tools erstellte EDMX-Datei, die mit Entity Framework bereitgestellt werden. Weitere Informationen finden Sie unter der [ \[MC-EDMX\]: Entity Data Model for Data Services Packaging Format](http://go.microsoft.com/fwlink/?LinkID=178833) Spezifikation.  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Generieren von Clientdatendienstklassen](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
 Das Tool DataSvcUtil.exe wird im [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Verzeichnis installiert. Dieses befindet sich meist unter C:\Windows\Microsoft.NET\Framework\v4.0. Bei 64-Bit-Systemen befindet es sich unter C:\Windows\Microsoft.NET\Framework64\v4.0. Sie können auch das Tool DataSvcUtil.exe zugreifen, von der Visual Studio-Eingabeaufforderung (klicken Sie auf **starten**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Visual Studio 2010**, Zeigen Sie auf **Visual Studio-Tools**, und klicken Sie dann auf **Visual Studio 2010-Eingabeaufforderung**).  
  
## <a name="syntax"></a>Syntax  
  
```  
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Option|Beschreibung|  
|------------|-----------------|  
|`/dataservicecollection`|Gibt an, dass der zum Binden von Objekten an Steuerelemente erforderliche Code auch generiert wird.|  
|`/help`<br /><br /> - oder - <br /><br /> `/?`|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|`/in:` *\<Datei >*|Gibt die CSDL- oder EDMX-Datei oder ein Verzeichnis an, in dem sich die Datei befindet.|  
|`/language:`[VB&#124;CSharp]|Gibt die Sprache für die erstellten Quellcodedateien an. Die Standardsprache ist C#.|  
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|  
|`/out:` *\<Datei >*|Gibt den Namen der Quellcodedatei an, die die generierten Clientdatendienstklassen enthält.|  
|`/uri:` *\<Zeichenfolge >*|Der URI, der die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed.|  
|`/version:`[1.0&#124;2.0]|Gibt die höchste akzeptierte Version von [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] an. Die Version wird basierend auf bestimmt die `DataServiceVersion` Attribut des Elements "DataService" in den Dienstmetadaten zurückgegebenen Daten. Weitere Informationen finden Sie unter [Datendienst-Versionskontrolle](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). Geben Sie bei der `/dataservicecollection` Parameter verwenden, müssen Sie auch angeben `/version:2.0` um die Datenbindung zu ermöglichen.|  
  
## <a name="see-also"></a>Siehe auch  
 [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 [Vorgehensweise: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
