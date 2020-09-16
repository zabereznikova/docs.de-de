---
title: WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, generating client data classes
- WCF Data Services, client library
- WCF Data Services, consuming
ms.assetid: 9d0af606-929b-4c03-b307-3ef5f705afce
ms.openlocfilehash: 600cb9a4f91ff2051f60ee86d4cb80cc5b404c61
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544296"
---
# <a name="wcf-data-service-client-utility-datasvcutilexe"></a>WCF Data Service-Clienthilfsprogramm ("DataSvcUtil.exe")

DataSvcUtil.exe ist ein von WCF Data Services bereitgestelltes Befehlszeilen Tool, das einen Open Data Protocol-Feed (odata) verwendet und die Client Datendienst Klassen generiert, die für den Zugriff auf einen Datendienst aus einer .NET Framework-Client Anwendung benötigt werden. Dieses Hilfsprogramm kann Datenklassen mit den folgenden Metadaten-Quellen generieren:

- Der Stamm-URI eines Datendiensts. Das Dienstprogramm fordert das Dienstmetadatendokument an, in dem das vom Datendienst verfügbar gemachte Datenmodell beschrieben wird. Weitere Informationen finden Sie unter [AtomPub (RFC5023)](https://tools.ietf.org/html/rfc5023#section-8).

- Eine Datenmodell Datei (CSDL), die mithilfe der konzeptionellen Schema Definitions Sprache (CSDL) definiert wird, wie in der Format Spezifikation " [ \[ MC-CSDL \] : konzeptionelle Schema Definitionsdatei](/openspecs/windows_protocols/mc-csdl/c03ad8c3-e8b7-4306-af96-a9e52bb3df12) " definiert.

- Eine mit den Entity Data Model-Tools erstellte EDMX-Datei, die mit Entity Framework bereitgestellt werden. Weitere Informationen finden Sie in der Spezifikation " [ \[ MC-edmx \] : Entity Data Model für Data Services Packungs Format](/openspecs/windows_protocols/mc-edmx/5dff5e25-56a1-408b-9d44-bff6634c7d16) ".

Weitere Informationen finden Sie unter Gewusst [wie: Manuelles Generieren von Client Datendienst Klassen](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).

Das DataSvcUtil.exe Tool ist im Verzeichnis .NET Framework installiert. In vielen Fällen befindet sich diese Datei unter " *c:\WINDOWS\Microsoft.Net\Framework\v4.0*". Bei 64-Bit-Systemen befindet sich diese Datei unter " *c:\WINDOWS\Microsoft.net\framework64\v4.0*". Sie können auch über Developer-Eingabeaufforderung für Visual Studio auf das DataSvcUtil.exe Tool zugreifen.

## <a name="syntax"></a>Syntax

```console
datasvcutil /out:file [/in:file | /uri:serviceuri] [/dataservicecollection] [/language:devlang] [/nologo] [/version:ver] [/help]
```

## <a name="parameters"></a>Parameter

|Option|BESCHREIBUNG|
|------------|-----------------|
|`/dataservicecollection`|Gibt an, dass der zum Binden von Objekten an Steuerelemente erforderliche Code auch generiert wird.|
|`/help`<br /><br /> - oder -<br /><br /> `/?`|Zeigt Befehlssyntax und Optionen für das Tool an.|
|`/in:` *\<file>*|Gibt die CSDL- oder EDMX-Datei oder ein Verzeichnis an, in dem sich die Datei befindet.|
|`/language:`[VB&#124;CSharp]|Gibt die Sprache für die erstellten Quellcodedateien an. Die Standardsprache ist C#.|
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|
|`/out:` *\<file>*|Gibt den Namen der Quellcodedatei an, die die generierten Clientdatendienstklassen enthält.|
|`/uri:` *\<string>*|Der URI des odata-Feeds.|
|`/version:`[1,0&#124;2,0]|Gibt die höchste akzeptierte Version von odata an. Die Version wird auf der Grundlage des- `DataServiceVersion` Attributs des DataService-Elements in den zurückgegebenen Datendienst Metadaten bestimmt. Weitere Informationen finden Sie unter [Data Service Versioning](data-service-versioning-wcf-data-services.md). Wenn Sie den- `/dataservicecollection` Parameter angeben, müssen Sie auch angeben, `/version:2.0` um die Datenbindung zu aktivieren.|

## <a name="see-also"></a>Siehe auch

- [Generieren der Datendienstclientbibliothek](generating-the-data-service-client-library-wcf-data-services.md)
- [Vorgehensweise: Hinzufügen eines Datendienstverweises](how-to-add-a-data-service-reference-wcf-data-services.md)
