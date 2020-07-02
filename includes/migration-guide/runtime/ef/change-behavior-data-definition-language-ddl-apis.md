---
ms.openlocfilehash: 4396ff43a48a23df29c5938b6bd2137d527b4ef5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620302"
---
### <a name="change-in-behavior-in-data-definition-language-ddl-apis"></a>Änderung des Verhaltens in DDL-APIs (Data Definition Language, Datendefinitionssprachen)

#### <a name="details"></a>Details

Das Verhalten von DDL-APIs beim Angeben von „AttachDBFilename“ hat sich wie folgt geändert:<ul><li>Verbindungszeichenfolgen müssen keinen „Initial Catalog“-Wert angeben. Zuvor waren „AttatchDBFilename“ und „Initial Catalog“ erforderlich.</li><li>Wenn „AttatchDBFilename“ und „Initial Catalog“ angegeben sind und die angegebene MDF-Datei vorhanden ist, gibt die <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>-Methode <code>true</code> zurück. Bislang hat sie <code>false</code> zurückgegeben.</li><li>Wenn „AttatchDBFilename“ und „Initial Catalog“ angegeben sind und die angegebene MDF-Datei vorhanden ist, werden die Dateien durch Aufrufen der <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>-Methode gelöscht.</li><li>Wird <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> aufgerufen, wenn die Verbindungszeichenfolge einen „AttachDBFilename“-Wert mit einer MDF-Datei und einem „Initial Catalog“ angibt, die beide nicht vorhanden sind, löst die Methode eine <xref:System.InvalidOperationException>-Ausnahme aus. Zuvor hat sie eine <xref:System.Data.SqlClient.SqlException>-Ausnahme ausgelöst.</li></ul>

#### <a name="suggestion"></a>Vorschlag

Diese Änderungen erleichtern das Erstellen von Tools und Anwendungen, die die DDL-APIs verwenden. Diese Änderungen können sich in den folgenden Szenarien auf die Anwendungskompatibilität auswirken:<ul><li>Der Benutzer schreibt Code, der einen <code>DROP DATABASE</code>-Befehl ausführt, anstatt direkt <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A> aufzurufen, wenn <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A><code>true</code> zurückgibt. Ist die Datenbank nicht angefügt, die MDF-Datei jedoch vorhanden, wird vorhandener Code hierdurch unbrauchbar.</li><li>Der Benutzer schreibt Code, der erwartet, dass die <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>-Methode eine <xref:System.Data.SqlClient.SqlException>- anstelle einer <xref:System.InvalidOperationException>-Ausnahme auslöst, wenn „Initial Catalog“ und MDF-Datei nicht vorhanden sind.</li></ul>

| name    | Wert       |
|:--------|:------------|
| Bereich   |Gering|
|Version|4.5|
|Typ|Laufzeit|
