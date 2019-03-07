---
title: WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: bb279e6fa16b82bffbebc777f791ce7a6e06255d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492646"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")

DataSvcUtil.exe ist ein Befehlszeilentool, das bereitgestellt, die von WCF Data Services, die benötigt eine [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed verwendet und generiert die Client-Datendienstklassen, die auf einen Datendienst aus einer .NET Framework-Clientanwendung benötigt werden. Dieses Hilfsprogramm kann Datenklassen mit den folgenden Metadaten-Quellen generieren:

-   Der Stamm-URI eines Datendiensts. Das Dienstprogramm fordert das Dienstmetadatendokument an, in dem das vom Datendienst verfügbar gemachte Datenmodell beschrieben wird. Weitere Informationen finden Sie unter [OData: Service Metadatendokument](https://go.microsoft.com/fwlink/?LinkId=186070).

-   Einer Datenmodelldatei (.csdl), mit der konzeptionellen Schemadefinitionssprache (CSDL) definiert werden, gemäß der [ \[MC-CSDL\]: Conceptual Schema Definition File Format](https://go.microsoft.com/fwlink/?LinkID=159072) Spezifikation.

-   Eine mit den Entity Data Model-Tools erstellte EDMX-Datei, die mit Entity Framework bereitgestellt werden. Weitere Informationen finden Sie unter den [ \[MC-EDMX\]: Entity Data Model für Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) Spezifikation.

Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Generieren von Clientdatendienstklassen](../../../../docs/framework/data/wcf/how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Das Tool DataSvcUtil.exe wird im [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Verzeichnis installiert. In vielen Fällen befindet sich diese *c:\WINDOWS\Microsoft.net\framework\v4.0"*. Für 64-Bit-Systemen befindet sich diese *C:\Windows\Microsoft.NET\Framework64\v4.0*. Sie können auch das Tool DataSvcUtil.exe von der Developer-Eingabeaufforderung für Visual Studio zugreifen.

## <a name="syntax"></a>Syntax

```
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parameter

|Option|Beschreibung|
|------------|-----------------|
|`/dataservicecollection`|Gibt an, dass der zum Binden von Objekten an Steuerelemente erforderliche Code auch generiert wird.|
|`/help`<br /><br /> - oder - <br /><br /> `/?`|Zeigt Befehlssyntax und Optionen für das Tool an.|
|`/in:` *\<file>*|Gibt die CSDL- oder EDMX-Datei oder ein Verzeichnis an, in dem sich die Datei befindet.|
|`/language:`[VB&#124;CSharp]|Gibt die Sprache für die erstellten Quellcodedateien an. Die Standardsprache ist C#.|
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|
|`/out:` *\<file>*|Gibt den Namen der Quellcodedatei an, die die generierten Clientdatendienstklassen enthält.|
|`/uri:` *\<string>*|Der URI des OData-Feed.|
|`/version:`[1.0&#124;2.0]|Gibt die höchste akzeptierte Version von OData. Die Version wird ermittelt, auf der Grundlage der `DataServiceVersion` -Attribut des Elements "DataService" in den Metadaten zurückgegebenen Daten. Weitere Informationen finden Sie unter [Datendienst-Versionskontrolle](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md). Bei Angabe der `/dataservicecollection` -Parameter müssen Sie auch angeben `/version:2.0` um die Datenbindung zu aktivieren.|

## <a name="see-also"></a>Siehe auch

- [Generieren der Datendienst-Clientbibliothek](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)
- [Vorgehensweise: Hinzufügen eines Datendienstverweises](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md)
