---
title: WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: de260e1a6b58fdbac1a2f0f40c7ec2e50b13644e
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975086"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")

DataSvcUtil. exe ist ein von WCF Data Services bereitgestelltes Befehlszeilen Tool, das einen Open Data Protocol-Feed (odata) verwendet und die Client Datendienst Klassen generiert, die für den Zugriff auf einen Datendienst aus einer .NET Framework Client Anwendung benötigt werden. Dieses Hilfsprogramm kann Datenklassen mit den folgenden Metadaten-Quellen generieren:

- Der Stamm-URI eines Datendiensts. Das Dienstprogramm fordert das Dienstmetadatendokument an, in dem das vom Datendienst verfügbar gemachte Datenmodell beschrieben wird. Weitere Informationen finden Sie unter [odata: dienstmetadatendokument](https://go.microsoft.com/fwlink/?LinkId=186070).

- Eine Datenmodell Datei (. CSDL), die mithilfe der konzeptionellen Schema Definitions Sprache (CSDL) definiert wird, wie in der [\[MC-CSDL\]: konzeptionelle Schema Definition-Datei Format](https://go.microsoft.com/fwlink/?LinkID=159072) Spezifikation definiert.

- Eine mit den Entity Data Model-Tools erstellte EDMX-Datei, die mit Entity Framework bereitgestellt werden. Weitere Informationen finden Sie in der Spezifikation [\[MC-edmx\]: Entity Data Model for Data Services Packaging Format](https://go.microsoft.com/fwlink/?LinkID=178833) .

Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Generieren von Client Datendienst Klassen](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Das Tool DataSvcUtil. exe wird im .NET Framework Verzeichnis installiert. In vielen Fällen befindet sich diese Datei unter " *c:\WINDOWS\Microsoft.Net\Framework\v4.0*". Bei 64-Bit-Systemen befindet sich diese Datei unter " *c:\WINDOWS\Microsoft.net\framework64\v4.0*". Sie können auch über Developer-Eingabeaufforderung für Visual Studio auf das Tool DataSvcUtil. exe zugreifen.

## <a name="syntax"></a>Syntax

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parameter

|Option|Beschreibung|
|------------|-----------------|
|`/dataservicecollection`|Gibt an, dass der zum Binden von Objekten an Steuerelemente erforderliche Code auch generiert wird.|
|`/help`<br /><br /> - oder -<br /><br /> `/?`|Zeigt Befehlssyntax und Optionen für das Tool an.|
|`/in:` *\<Datei >*|Gibt die CSDL- oder EDMX-Datei oder ein Verzeichnis an, in dem sich die Datei befindet.|
|`/language:`[VB&#124;CSharp]|Gibt die Sprache für die erstellten Quellcodedateien an. Die Standardsprache ist C#.|
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|
|`/out:` *\<Datei >*|Gibt den Namen der Quellcodedatei an, die die generierten Clientdatendienstklassen enthält.|
|`/uri:` *\<Zeichenfolge >*|Der URI des odata-Feeds.|
|`/version:`[1,0&#124;2,0]|Gibt die höchste akzeptierte Version von odata an. Die Version wird basierend auf dem `DataServiceVersion`-Attribut des DataService-Elements in den zurückgegebenen Datendienst Metadaten bestimmt. Weitere Informationen finden Sie unter [Data Service Versioning](data-service-versioning-wcf-data-services.md). Wenn Sie den `/dataservicecollection`-Parameter angeben, müssen Sie auch `/version:2.0` angeben, um die Datenbindung zu aktivieren.|

## <a name="see-also"></a>Siehe auch

- [Generieren der Datendienst-Clientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)
- [Vorgehensweise: Hinzufügen eines Datendienstverweises](how-to-add-a-data-service-reference-wcf-data-services.md)
