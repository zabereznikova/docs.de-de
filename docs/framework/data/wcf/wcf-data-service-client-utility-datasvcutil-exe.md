---
title: WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 7632362339cf9e23599f4f688f98cbc1d0b32114
ms.sourcegitcommit: 5ae5a1a9520b8b8b6164ad728d396717f30edafc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2019
ms.locfileid: "70894251"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")

DataSvcUtil. exe ist ein Befehlszeilen Tool, das von WCF Data Services bereitgestellt wird [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] , das einen-Feed verwendet und die Client Datendienst Klassen generiert, die für den Zugriff auf einen Datendienst aus einer .NET Framework Client Anwendung benötigt werden. Dieses Hilfsprogramm kann Datenklassen mit den folgenden Metadaten-Quellen generieren:

- Der Stamm-URI eines Datendiensts. Das Dienstprogramm fordert das Dienstmetadatendokument an, in dem das vom Datendienst verfügbar gemachte Datenmodell beschrieben wird. Weitere Informationen finden [Sie unter odata: Dienstmetadatendokument](https://go.microsoft.com/fwlink/?LinkId=186070).

- Eine Datenmodell Datei (CSDL), die mithilfe der CSDL (konzeptionelle Schema Definitions Sprache) definiert wird, wie in der [ \["MC-CSDL\]" definiert: Format](https://go.microsoft.com/fwlink/?LinkID=159072) Spezifikation der konzeptionellen Schema Definitionsdatei.

- Eine mit den Entity Data Model-Tools erstellte EDMX-Datei, die mit Entity Framework bereitgestellt werden. Weitere Informationen finden Sie unter [ \[MC-edmx\]: Entity Data Model für die Spezifikation des](https://go.microsoft.com/fwlink/?LinkID=178833) Data Services Packungs Formats.

Weitere Informationen finden Sie unter [Vorgehensweise: Manuelles Generieren von Client Daten](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)Dienst Klassen.

Das Tool DataSvcUtil. exe wird im .NET Framework Verzeichnis installiert. In vielen Fällen befindet sich diese Datei unter " *c:\WINDOWS\Microsoft.Net\Framework\v4.0*". Bei 64-Bit-Systemen befindet sich diese Datei unter " *c:\WINDOWS\Microsoft.net\framework64\v4.0*". Sie können auch über Developer-Eingabeaufforderung für Visual Studio auf das Tool DataSvcUtil. exe zugreifen.

## <a name="syntax"></a>Syntax

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parameter

|Option|Beschreibung|
|------------|-----------------|
|`/dataservicecollection`|Gibt an, dass der zum Binden von Objekten an Steuerelemente erforderliche Code auch generiert wird.|
|`/help`<br /><br /> -oder-<br /><br /> `/?`|Zeigt Befehlssyntax und Optionen für das Tool an.|
|`/in:` *\<file>*|Gibt die CSDL- oder EDMX-Datei oder ein Verzeichnis an, in dem sich die Datei befindet.|
|`/language:`[VB&#124;CSharp]|Gibt die Sprache für die erstellten Quellcodedateien an. Die Standardsprache ist C#.|
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|
|`/out:` *\<file>*|Gibt den Namen der Quellcodedatei an, die die generierten Clientdatendienstklassen enthält.|
|`/uri:` *\<string>*|Der URI des odata-Feeds.|
|`/version:`[1.0&#124;2.0]|Gibt die höchste akzeptierte Version von odata an. Die Version wird auf der Grundlage des `DataServiceVersion` -Attributs des DataService-Elements in den zurückgegebenen Datendienst Metadaten bestimmt. Weitere Informationen finden Sie unter [Data Service Versioning](data-service-versioning-wcf-data-services.md). Wenn Sie den- `/dataservicecollection` Parameter angeben, müssen Sie auch `/version:2.0` angeben, um die Datenbindung zu aktivieren.|

## <a name="see-also"></a>Siehe auch

- [Generieren der Datendienst-Clientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)
- [Vorgehensweise: Hinzufügen eines Datendienst Verweises](how-to-add-a-data-service-reference-wcf-data-services.md)
