---
title: Oracle-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 89a75de8-dee8-45e2-a97f-254d7e62e7e1
ms.openlocfilehash: 342c4cbe994eb983713be0f258e3a029df6739f8
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43886083"
---
# <a name="oracle-schema-collections"></a>Oracle-Schemaauflistungen
Der Microsoft .NET Framework-Datenanbieter für Oracle unterstützt außer den allgemeinen Schemaauflistungen die folgenden spezifischen Schemaauflistungen:  
  
-   Columns  
  
-   Indexes  
  
-   IndexColumns  
  
-   Verfahren  
  
-   Sequenzen  
  
-   Synonyms  
  
-   Tabellen  
  
-   Benutzer  
  
-   Ansichten  
  
-   Funktionen  
  
-   Pakete  
  
-   PackageBodies  
  
-   Argumente  
  
-   UniqueKeys  
  
-   PrimaryKeys  
  
-   ForeignKeys  
  
-   ForeignKeyColumns  
  
-   ProcedureParameters  
  
## <a name="columns"></a>Columns  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer der Tabelle, der Ansicht oder des Clusters.|  
|TABLE_NAME|Zeichenfolge|Name der Tabelle, der Ansicht oder des Clusters.|  
|COLUMN_NAME|Zeichenfolge|Spaltenname.|  
|ID|Decimal|Folgenummer der Spalte, nach Erstellung.|  
|Datentyp|Zeichenfolge|Datentyp der Spalte.|  
|LENGTH|Decimal|Länge der Spalte in Byte.|  
|PRECISION|Decimal|Decimal-Genauigkeit für Datentyp NUMBER, binary- Genauigkeit für Datentyp FLOAT, NULL für alle anderen Datentypen.|  
|SCALE|Decimal|Stellen rechts vom Dezimaltrennzeichen einer Zahl.|  
|NULLABLE|Zeichenfolge|Gibt an, ob NULL in einer Spalte zulässig ist. Der Wert ist N, wenn für die Spalte eine NOT NULL-Einschränkung vorliegt oder wenn die Spalte Teil eines PRIMARY KEY ist.|  
  
## <a name="indexes"></a>Indexes  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer des Indexes|  
|INDEX_NAME|Zeichenfolge|Name des Indexes.|  
|INDEX_TYPE|Zeichenfolge|Typ des Indexes (NORMAL, BITMAP, FUNCTION-BASED NORMAL, FUNCTION-BASED BITMAP oder DOMAIN).|  
|TABLE_OWNER|Zeichenfolge|Besitzer des Objekts im Index.|  
|TABLE_NAME|Zeichenfolge|Name des Objekts im Index.|  
|TABLE_TYPE|Zeichenfolge|Typ des Objekts im Index (z. B. TABLE, CLUSTER).|  
|UNIQUENESS|Zeichenfolge|Ob der Index UNIQUE oder NONUNIQUE ist.|  
|COMPRESSION|Zeichenfolge|Ob der Index ENABLED oder DISABLED ist.|  
|PREFIX_LENGTH|Decimal|Anzahl der Spalten im Präfix des Komprimierungsschlüssels.|  
|TABLESPACE_NAME|Zeichenfolge|Name des Tabellenbereichs, der den Index enthält.|  
|INI_TRANS|Decimal|Ursprüngliche Anzahl von Transaktionen.|  
|MAX_TRANS|Decimal|Maximale Anzahl von Transaktionen.|  
|INITIAL_EXTENT|Decimal|Anfangsgröße des Bereichs.|  
|NEXT_EXTENT|Decimal|Größe von Erweiterungsbereichen.|  
|MIN_EXTENTS|Decimal|Minimale Anzahl von Erweiterungsbereichen im Segment.|  
|MAX_EXTENTS|Decimal|Maximale Anzahl von Erweiterungsbereichen im Segment.|  
|PCT_INCREASE|Decimal|Prozentuale Erhöhung der Größe des Erweiterungsbereichs.|  
|PCT_THRESHOLD|Decimal|Prozentualer Schwellenwert des pro Indexeintag zulässigen Blockraums.|  
|INCLUDE_COLUMN|Decimal|Spalten-ID der letzten Spalte, die im Primärschlüsselindex (ohne Überlauf) einer nach dem Index sortierten Tabelle enthalten sein soll. Diese Spalte wird der Spalte COLUMN_ID der *_TAB_COLUMNS-Datenwörterbuchansichten zugeordnet.|  
|FREELISTS|Decimal|Anzahl von Prozess-Freelists, die diesem Segment zugewiesen sind.|  
|FREELIST_GROUPS|Decimal|Anzahl von Freelist-Gruppen, die diesem Segment zugewiesen sind.|  
|PCT_FREE|Decimal|Minimaler Prozentsatz des freien Speicherplatzes in einem Block.|  
|LOGGING|Zeichenfolge|Informationen zur Protokollierung.|  
|BLEVEL|Decimal|B*-Strukturebene: Tiefe des Indexes von dessen Stammblock bis zu seinem Endblock. Eine Tiefe von 0 (null) gibt an, dass der Stammblock auch der Endblock ist.|  
|LEAF_BLOCKS|Decimal|Anzahl von Endblöcken im Index.|  
|DISTINCT_KEYS|Decimal|Anzahl der unterschiedlichen Werte im Index. Bei Indizes, die die UNIQUE-Einschränkung und die PRIMARY KEY-Einschränkung erzwingen, entspricht dieser Wert der Anzahl von Zeilen in der Tabelle (USER_TABLES.NUM_ROWS).|  
|AVG_LEAF_BLOCKS_PER_KEY|Decimal|Durchschnittliche Anzahl von Endblöcken, wobei jeder unterschiedliche Wert im Index auf die nächste ganze Zahl gerundet angezeigt wird. Bei Indizes, die die UNIQUE-Eigenschaft und die PRIMARY KEY-Eigenschaft erzwingen, ist dieser Wert immer 1.|  
|AVG_DATA_BLOCKS_PER_KEY|Decimal|Durchschnittliche Anzahl von Datenblöcken in der Tabelle, auf die im Index durch einen eindeutigen, auf die nächste ganze Zahl gerundeten Wert verwiesen wird. Bei der Statistik handelt es sich um die durchschnittliche Anzahl von Datenblöcken mit Zeilen, die einen angegebenen Wert für die Spalten im Index enthalten.|  
|CLUSTERING_FACTOR|Decimal|Gibt die Unregelmäßigkeit der Zeilen in der Tabelle anhand der Werte des Indexes an.|  
|STATUS|Zeichenfolge|Gibt an, ob ein nicht partitionierter Index VALID oder UNUSABLE ist.|  
|NUM_ROWS|Decimal|Anzahl von Zeilen im Index.|  
|SAMPLE_SIZE|Decimal|Größe des Beispiels, das zum Analysieren des Indexes verwendet wird.|  
|LAST_ANALYZED|DateTime|Datum, an dem dieser Index zuletzt analysiert wurde.|  
|DEGREE|Zeichenfolge|Anzahl von Threads pro Instanz zum Durchsuchen des Indexes.|  
|INSTANCES|Zeichenfolge|Anzahl von Instanzen, in den die Indizes durchsucht werden sollen.|  
|PARTITIONED|Zeichenfolge|Gibt an, ob dieser Index partitioniert ist (Ja &#124; Nein).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob sich der Index in einer temporären Tabelle befindet.|  
|GENERATED|Zeichenfolge|Gibt an, ob der Name des Indexes vom System generiert wird (Y&#124;N).|  
|SECONDARY|Zeichenfolge|Gibt an, ob der Index ein sekundäres Objekt von der ODCIIndexCreate-Methode der Oracle9i Data Cartridge erstellt wurde (Y&#124;N).|  
|BUFFER_POOL|Zeichenfolge|Name des Standardpufferpools, der für die Indexblöcke verwendet wird.|  
|USER_STATS|Zeichenfolge|Gibt an, ob die Statistik direkt vom Benutzer eingegeben wurde.|  
|DURATION|Zeichenfolge|Gibt die Dauer einer temporären Tabelle an: 1) SYS$SESSION: Die Zeilen werden für die Dauer der Sitzung beibehalten. 2) SYS$TRANSACTION: Die Zeilen werden nach dem COMMIT gelöscht. 3) NULL für eine dauerhafte Tabelle.|  
|PCT_DIRECT_ACCESS|Decimal|Der prozentuale Anteil von Reihen mit dem geschätzten Wert VALID bei einem sekundären Index in einer nach dem Index sortierten Tabelle |  
|ITYP_OWNER|Zeichenfolge|Der Besitzer des Indextyps eines Domänenindexes.|  
|ITYP_NAME|Zeichenfolge|Der Name des Indextyps eines Domänenindexes.|  
|PARAMETERS|Zeichenfolge|Die Parameterzeichenfolge eines Domänenindexes.|  
|GLOBAL_STATS|Zeichenfolge|Gibt bei partitionierten Indizes an, ob Statistiken durch eine Analyse des gesamten Indexes erstellt wurden (YES) oder ob sie anhand von Statistiken zugrunde liegender Indexpartitionen und Unterpartitionen geschätzt wurden (NO).|  
|DOMIDX_STATUS|Zeichenfolge|Gibt den Status des Domänenindexes an. NULL: Bei dem angegebenen Index handelt es sich nicht um einen Domänenindex. VALID: Bei dem Index handelt es sich um einen gültigen Domänenindex. IDXTYP_INVLD: Der Indextyp dieses Domänenindexes ist ungültig.|  
|DOMIDX_OPSTATUS|Zeichenfolge|Gibt den Status eines Vorgangs an, der für einen Domänenindex durchgeführt wurde. NULL: Bei dem angegebenen Index handelt es sich nicht um einen Domänenindex. VALID: Der Vorgang wurde fehlerfrei durchgeführt. FAILED: Bei diesem Vorgang ist ein Fehler aufgetreten.|  
|FUNCIDX_STATUS|Zeichenfolge|Gibt den Status eines funktionsbasierten Indexes an. NULL: Dies ist kein funktionsbasierter Index. ENABLED: Der funktionsbasierte Index ist aktiviert. DISABLED: Der funktionsbasierte Index ist deaktiviert.|  
|JOIN_INDEX|Zeichenfolge|Gibt an, ob es sich hierbei um einen Joinindex handelt oder nicht.|  
  
## <a name="indexcolumns"></a>IndexColumns  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|INDEX_OWNER|Zeichenfolge|Besitzer des Indexes.|  
|INDEX_NAME|Zeichenfolge|Name des Indexes.|  
|TABLE_OWNER|Zeichenfolge|Besitzer der Tabelle oder des Clusters.|  
|TABLE_NAME|Zeichenfolge|Name der Tabelle oder des Clusters.|  
|COLUMN_NAME|Zeichenfolge|Spaltenname oder Attribut der Objekttypspalte.|  
|COLUMN_POSITION|Decimal|Position der Spalte oder des Attributs im Index.|  
|COLUMN_LENGTH|Decimal|Länge der Spalte im Index.|  
|CHAR_LENGTH|Decimal|Maximale Codepunktlänge der Spalte.|  
|DESCEND|Zeichenfolge|Gibt an, ob die Spalte in absteigender Reihenfolge sortiert wird.|  
  
## <a name="procedures"></a>Verfahren  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT_NAME|Zeichenfolge|Name des Objekts.|  
|SUBOBJECT_NAME|Zeichenfolge|Name des Unterobjekts (z. B. Partition).|  
|OBJECT_ID|Decimal|Wörterbuchobjektnummer des Objekts.|  
|DATA_OBJECT_ID|Decimal|Wörterbuchobjektnummer des Segments, in dem das Objekt enthalten ist.|  
|LAST_DDL_TIME|DateTime|Timestamp für die letzte Änderung des Objekts durch einen DDL-Befehl (einschließlich Gewährungen und Widerrufen).|  
|TIMESTAMP|Zeichenfolge|Timestamp zur Spezifikation des Objekts (Zeichendaten).|  
|STATUS|Zeichenfolge|Status des Objekts (VALID, INVALID oder N/A).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob das Objekt temporär ist (von der aktuellen Sitzung können nur Daten angezeigt werden, die von ihr in diesem Objekt abgelegt wurden).|  
|GENERATED|Zeichenfolge|Wurde der Name dieses Objekts vom System generiert? (Y &#124; N).|  
|SECONDARY|Zeichenfolge|Ob dies ein sekundäres Objekt, die von der ODCIIndexCreate-Methode der Oracle9i Data Cartridge erstellt wurde (Y &#124; N).|  
|CREATED|DateTime|Das Datum, an dem das Objekt erstellt wurde.|  
  
## <a name="sequences"></a>Sequenzen  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|SEQUENCE_OWNER|Zeichenfolge|Name des Besitzers der Sequenz.|  
|SEQUENCE_NAME|Zeichenfolge|Name der Sequenz.|  
|MIN_VALUE|Decimal|Niedrigster Wert der Sequenz.|  
|MAX_VALUE|Decimal|Höchster Wert der Sequenz.|  
|INCREMENT_BY|Decimal|Wert, um den die Sequenz inkrementiert wird.|  
|CYCLE_FLAG|Zeichenfolge|Führt Sequenz-Wrapping beim Erreichen der Beschränkung aus.|  
|ORDER_FLAG|Zeichenfolge|Sequenznummern werden der Reihe nach generiert.|  
|CACHE_SIZE|Decimal|Anzahl der Sequenznummern, die zwischengespeichert werden soll.|  
|LAST_NUMBER|Decimal|Letzte Sequenznummer, die auf den Datenträger geschrieben wird. Wenn bei einer Sequenz die Zwischenspeicherung verwendet wird, wird die auf den Datenträger geschriebene Nummer zuletzt im Sequenzcache positioniert. Diese Nummer ist wahrscheinlich größer als die zuletzt verwendete Sequenznummer.|  
  
## <a name="synonyms"></a>Synonyms  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer des Synonyms.|  
|SYNONYM_NAME|Zeichenfolge|Name des Synonyms.|  
|TABLE_OWNER|Zeichenfolge|Besitzer des Objekts, auf das das Synonym verweist.|  
|TABLE_NAME|Zeichenfolge|Name des Objekts, auf das das Synonym verweist.|  
|DB_LINK|Zeichenfolge|Name des ggf. vorhandenen Datenbanklinks, auf den verwiesen wird.|  
  
## <a name="tables"></a>Tabellen  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer der Tabelle.|  
|TABLE_NAME|Zeichenfolge|Name der Tabelle.|  
|TYPE|Zeichenfolge|Tabellentyp.|  
  
## <a name="users"></a>Benutzer  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|NAME|Zeichenfolge|Name des Benutzers.|  
|ID|Decimal|ID-Nummer des Benutzers.|  
|CREATEDATE|DateTime|Datum der Benutzererstellung.|  
  
## <a name="views"></a>Ansichten  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer der Ansicht.|  
|VIEW_NAME|Zeichenfolge|Name der Ansicht.|  
|TEXT_LENGTH|Decimal|Länge des Anzeigetexts.|  
|TEXT|Zeichenfolge|Anzeigetext.|  
|TYPE_TEXT_LENGTH|Decimal|Länge der Typklausel der typisierten Ansicht.|  
|TYPE_TEXT|Zeichenfolge|Typklausel der typisierten Ansicht.|  
|OID_TEXT_LENGTH|Decimal|Länge der WITH OID-Klausel der typisierten Ansicht.|  
|OID_TEXT|Zeichenfolge|WITH OID-Klausel der typisierten Ansicht.|  
|VIEW_TYPE_OWNER|Zeichenfolge|Besitzer des Typs der Ansicht, wenn es sich bei der Ansicht um eine typisierte Ansicht handelt.|  
|VIEW_TYPE|Zeichenfolge|Typ der Ansicht, wenn es sich bei der Ansicht um eine typisierte Ansicht handelt.|  
|SUPERVIEW_NAME|Zeichenfolge|Name der Überblicksansicht.|  
  
## <a name="functions"></a>Funktionen  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT_NAME|Zeichenfolge|Name des Objekts.|  
|SUBOBJECT_NAME|Zeichenfolge|Name des Unterobjekts (z. B. Partition).|  
|OBJECT_ID|Decimal|Wörterbuchobjektnummer des Objekts.|  
|DATA_OBJECT_ID|Decimal|Wörterbuchobjektnummer des Segments, in dem das Objekt enthalten ist.|  
|OBJECT_TYPE|Zeichenfolge|Typ des Objekts.|  
|CREATED|DateTime|Das Datum, an dem das Objekt erstellt wurde.|  
|LAST_DDL_TIME|DateTime|Timestamp für die letzte Änderung des Objekts durch einen DDL-Befehl (einschließlich Gewährungen und Widerrufen).|  
|TIMESTAMP|Zeichenfolge|Timestamp zur Spezifikation des Objekts (Zeichendaten).|  
|STATUS|Zeichenfolge|Status des Objekts (VALID, INVALID oder N/A).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob das Objekt temporär ist (von der aktuellen Sitzung können nur Daten angezeigt werden, die von ihr in diesem Objekt abgelegt wurden).|  
|GENERATED|Zeichenfolge|Wurde der Name dieses Objekts vom System generiert? (Y &#124; N).|  
|SECONDARY|Zeichenfolge|Ob dies ein sekundäres Objekt, die von der ODCIIndexCreate-Methode der Oracle9i Data Cartridge erstellt wurde (Y &#124; N).|  
  
## <a name="packages"></a>Pakete  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT_NAME|Zeichenfolge|Name des Objekts.|  
|SUBOBJECT_NAME|Zeichenfolge|Name des Unterobjekts (z. B. Partition).|  
|OBJECT_ID|Decimal|Wörterbuchobjektnummer des Objekts.|  
|DATA_OBJECT_ID|Decimal|Wörterbuchobjektnummer des Segments, in dem das Objekt enthalten ist.|  
|LAST_DDL_TIME|DateTime|Timestamp für die letzte Änderung des Objekts durch einen DDL-Befehl (einschließlich Gewährungen und Widerrufen).|  
|TIMESTAMP|Zeichenfolge|Timestamp zur Spezifikation des Objekts (Zeichendaten).|  
|STATUS|Zeichenfolge|Status des Objekts (VALID, INVALID oder N/A).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob das Objekt temporär ist (von der aktuellen Sitzung können nur Daten angezeigt werden, die von ihr in diesem Objekt abgelegt wurden).|  
|GENERATED|Zeichenfolge|Wurde der Name dieses Objekts vom System generiert? (Y &#124; N).|  
|SECONDARY|Zeichenfolge|Ob dies ein sekundäres Objekt, die von der ODCIIndexCreate-Methode der Oracle9i Data Cartridge erstellt wurde (Y &#124; N).|  
|CREATED|DateTime|Das Datum, an dem das Objekt erstellt wurde.|  
  
## <a name="packagebodies"></a>PackageBodies  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT_NAME|Zeichenfolge|Name des Objekts.|  
|SUBOBJECT_NAME|Zeichenfolge|Name des Unterobjekts (z. B. Partition).|  
|OBJECT_ID|Decimal|Wörterbuchobjektnummer des Objekts.|  
|DATA_OBJECT_ID|Decimal|Wörterbuchobjektnummer des Segments, in dem das Objekt enthalten ist.|  
|LAST_DDL_TIME|DateTime|Timestamp für die letzte Änderung des Objekts durch einen DDL-Befehl (einschließlich Gewährungen und Widerrufen).|  
|TIMESTAMP|Zeichenfolge|Timestamp zur Spezifikation des Objekts (Zeichendaten).|  
|STATUS|Zeichenfolge|Status des Objekts (VALID, INVALID oder N/A).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob das Objekt temporär ist (von der aktuellen Sitzung können nur Daten angezeigt werden, die von ihr in diesem Objekt abgelegt wurden).|  
|GENERATED|Zeichenfolge|Wurde der Name dieses Objekts vom System generiert? (Y &#124; N).|  
|SECONDARY|Zeichenfolge|Ob dies ein sekundäres Objekt, die von der ODCIIndexCreate-Methode der Oracle9i Data Cartridge erstellt wurde (Y &#124; N).|  
|CREATED|DateTime|Das Datum, an dem das Objekt erstellt wurde.|  
  
## <a name="arguments"></a>Argumente  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Name des Besitzers des Objekts.|  
|PACKAGE_NAME|Zeichenfolge|Name des Pakets.|  
|OBJECT_NAME|Zeichenfolge|Name der Prozedur oder Funktion.|  
|ARGUMENT_NAME|Zeichenfolge|Name des Arguments.|  
|POSITION|Decimal|Position in der Argumentliste oder NULL für den Rückgabewert einer Funktion.|  
|SEQUENCE|Decimal|Argumentsequenz einschließlich aller geschachtelten Ebenen.|  
|DEFAULT_VALUE|Zeichenfolge|Standardwert für das Argument.|  
|DEFAULT_LENGTH|Decimal|Länge des Standardwerts für das Argument.|  
|IN_OUT|Zeichenfolge|Argumentrichtung (IN, OUT oder IN/OUT).|  
|DATA_LENGTH|Decimal|Länge der Spalte in Byte.|  
|DATA_PRECISION|Decimal|Länge in Dezimalstellen (NUMBER) oder Binärzahlen (FLOAT).|  
|DATA_SCALE|Decimal|Stellen rechts vom Dezimaltrennzeichen einer Zahl.|  
|DATA_TYPE|Zeichenfolge|Datentyp des Arguments.|  
  
## <a name="uniquekeys"></a>UniqueKeys  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|CONSTRAINT_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|TABLE_NAME|Zeichenfolge|Name, der der Tabelle (oder Ansicht) mit der Einschränkungsdefinition zugeordnet ist.|  
|SEARCH_CONDITION|Zeichenfolge|Text der Suchbedingung für eine CHECK-Einschränkung.|  
|R_OWNER|Zeichenfolge|Besitzer einer Tabelle, auf die in einer referenziellen Einschränkung verwiesen wird.|  
|R_CONSTRAINT_NAME|Zeichenfolge|Name der Definition der UNIQUE-Einschränkung für die Tabelle, auf die verwiesen wird.|  
|DELETE_RULE|Zeichenfolge|Löschregel für eine referenzielle Einschränkung (CASCADE oder NO ACTION).|  
|STATUS|Zeichenfolge|Erzwingungsstatus einer Einschränkung (ENABLED oder DISABLED).|  
|DEFERRABLE|Zeichenfolge|Gibt an, ob die Einschränkung verzögert werden kann.|  
|VALIDATED|Zeichenfolge|Gibt an, ob die Einschränkung bei allen Daten berücksichtigt wird (VALIDATED oder NOT VALIDATED).|  
|GENERATED|Zeichenfolge|Gibt an, ob der Name einer Einschränkung vom Benutzer oder vom System generiert wurde.|  
|BAD|Zeichenfolge|Der Wert YES gibt an, dass diese Einschränkung ein Jahrhundert nicht eindeutig angibt. Um aufgrund dieser Mehrdeutigkeit entstehende Fehler zu vermeiden, schreiben Sie die Einschränkung mithilfe der TO_DATE-Funktion mit einer vierstelligen Jahreszahl neu.|  
|RELY|Zeichenfolge|Gibt an, ob eine aktivierte Einschränkung erzwungen oder nicht erzwungen ist.|  
|LAST_CHANGE|DateTime|Gibt an, wann die Einschränkung zuletzt aktiviert oder deaktiviert wurde.|  
|INDEX_OWNER|Zeichenfolge|Name des Benutzers, dem der Index gehört.|  
|INDEX_NAME|Zeichenfolge|Name des Indexes.|  
  
## <a name="primarykeys"></a>PrimaryKeys  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|CONSTRAINT_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|TABLE_NAME|Zeichenfolge|Name, der der Tabelle (oder Ansicht) mit der Einschränkungsdefinition zugeordnet ist.|  
|SEARCH_CONDITION|Zeichenfolge|Text der Suchbedingung für eine CHECK-Einschränkung.|  
|R_OWNER|Zeichenfolge|Besitzer einer Tabelle, auf die in einer referenziellen Einschränkung verwiesen wird.|  
|R_CONSTRAINT_NAME|Zeichenfolge|Name der Definition der UNIQUE-Einschränkung für die Tabelle, auf die verwiesen wird.|  
|DELETE_RULE|Zeichenfolge|Löschregel für eine referenzielle Einschränkung (CASCADE oder NO ACTION).|  
|STATUS|Zeichenfolge|Erzwingungsstatus einer Einschränkung (ENABLED oder DISABLED).|  
|DEFERRABLE|Zeichenfolge|Gibt an, ob die Einschränkung verzögert werden kann.|  
|VALIDATED|Zeichenfolge|Gibt an, ob die Einschränkung bei allen Daten berücksichtigt wird (VALIDATED oder NOT VALIDATED).|  
|GENERATED|Zeichenfolge|Gibt an, ob der Name einer Einschränkung vom Benutzer oder vom System generiert wurde.|  
|BAD|Zeichenfolge|Der Wert YES gibt an, dass diese Einschränkung ein Jahrhundert nicht eindeutig angibt. Um aufgrund dieser Mehrdeutigkeit entstehende Fehler zu vermeiden, schreiben Sie die Einschränkung mithilfe der TO_DATE-Funktion mit einer vierstelligen Jahreszahl neu.|  
|RELY|Zeichenfolge|Gibt an, ob eine aktivierte Einschränkung erzwungen oder nicht erzwungen ist.|  
|LAST_CHANGE|DateTime|Gibt an, wann die Einschränkung zuletzt aktiviert oder deaktiviert wurde.|  
|INDEX_OWNER|Zeichenfolge|Name des Benutzers, dem der Index gehört.|  
|INDEX_NAME|Zeichenfolge|Name des Indexes.|  
  
## <a name="foreignkeys"></a>ForeignKeys  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|PRIMARY_KEY_CONSTRAINT_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|PRIMARY_KEY_OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|PRIMARY_KEY_TABLE_NAME|Zeichenfolge|Name, der der Tabelle (oder Ansicht) mit der Einschränkungsdefinition zugeordnet ist.|  
|FOREIGN_KEY_OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|FOREIGN_KEY_CONSTRIANT_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|FOREIGN_KEY_TABLE_NAME|Zeichenfolge|Name, der der Tabelle (oder Ansicht) mit der Einschränkungsdefinition zugeordnet ist.|  
|SEARCH_CONDITION|Zeichenfolge|Text der Suchbedingung für eine CHECK-Einschränkung.|  
|R_OWNER|Zeichenfolge|Besitzer einer Tabelle, auf die in einer referenziellen Einschränkung verwiesen wird.|  
|R_CONSTRAINT_NAME|Zeichenfolge|Name der Definition der UNIQUE-Einschränkung für die Tabelle, auf die verwiesen wird.|  
|DELETE_RULE|Zeichenfolge|Löschregel für eine referenzielle Einschränkung (CASCADE oder NO ACTION).|  
|STATUS|Zeichenfolge|Erzwingungsstatus einer Einschränkung (ENABLED oder DISABLED).|  
|VALIDATED|Zeichenfolge|Gibt an, ob die Einschränkung bei allen Daten berücksichtigt wird (VALIDATED oder NOT VALIDATED).|  
|GENERATED|Zeichenfolge|Gibt an, ob der Name einer Einschränkung vom Benutzer oder vom System generiert wurde.|  
|RELY|Zeichenfolge|Gibt an, ob eine aktivierte Einschränkung erzwungen oder nicht erzwungen ist.|  
|LAST_CHANGE|DateTime|Gibt an, wann die Einschränkung zuletzt aktiviert oder deaktiviert wurde.|  
|INDEX_OWNER|Zeichenfolge|Name des Benutzers, dem der Index gehört.|  
|INDEX_NAME|Zeichenfolge|Name des Indexes.|  
  
## <a name="foreignkeycolumns"></a>ForeignKeyColumns  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|CONSTRAINT_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|TABLE_NAME|Zeichenfolge|Name der Tabelle mit der Einschränkungsdefinition.|  
|COLUMN_NAME|Zeichenfolge|Name der Spalte oder des Attributs der Objekttypspalte, die in der Einschränkungsdefinition angegeben ist.|  
|POSITION|Decimal|Ursprüngliche Position der Spalte oder des Attributs in der Definition des Objekts.|  
  
## <a name="procedureparameters"></a>ProcedureParameters  
  
|Spaltenname|DataType|Beschreibung|  
|----------------|--------------|-----------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT_NAME|Zeichenfolge|Name der Prozedur oder Funktion.|  
|PACKAGE_NAME|Zeichenfolge|Name der Prozedur oder Funktion.|  
|OBJECT_ID|Decimal|Objektnummer des Objekts.|  
|OVERLOAD|Zeichenfolge|Eindeutiger Bezeichner bei Überladungen.|  
|ARGUMENT_NAME|Zeichenfolge|Name des Arguments.|  
|POSITION|Decimal|Position in der Argumentliste oder NULL für den Rückgabewert einer Funktion.|  
|SEQUENCE|Decimal|Argumentsequenz einschließlich aller geschachtelten Ebenen.|  
|DATA_LEVEL|Decimal|Schachtelungstiefe des Arguments für zusammengesetzte Typen.|  
|DATA_TYPE|Zeichenfolge|Datentyp des Arguments.|  
|DEFAULT_VALUE|Zeichenfolge|Standardwert für das Argument.|  
|DEFAULT_LENGTH|Decimal|Länge des Standardwerts für das Argument.|  
|IN_OUT|Zeichenfolge|Argumentrichtung (IN, OUT oder IN/OUT).|  
|DATA_LENGTH|Decimal|Länge der Spalten (in Byte).|  
|DATA_PRECISION|Decimal|Länge in Dezimalstellen (NUMBER) oder Binärzahlen (FLOAT).|  
|DATA_SCALE|Decimal|Stellen rechts vom Dezimaltrennzeichen einer Zahl.|  
|RADIX|Decimal|Argumentbasis für eine Zahl.|  
|CHARACTER_SET_NAME|Zeichenfolge|Name des Zeichensatzes für das Argument.|  
|TYPE_OWNER|Zeichenfolge|Besitzer des Argumenttyps.|  
|TYPE_NAME|Zeichenfolge|Name des Argumenttyps. Wenn es sich bei dem Typ um einen im Paket befindlichen lokalen Typ handelt (d. h. er ist in einer Paketspezifikation deklariert), wird in dieser Spalte der Name des Pakets angezeigt.|  
|TYPE_SUBNAME|Zeichenfolge|Nur bei im Paket befindlichen lokalen Typen relevant. Zeigt den Namen des Typs an, der im in der Spalte TYPE_NAME angegebenen Paket deklariert ist.|  
|TYPE_LINK|Zeichenfolge|Nur bei im Paket befindlichen lokalen Typen relevant, wenn es sich bei dem in der Spalte TYPE_NAME angegebenen Paket um ein Remotepaket handelt. In dieser Spalte wird der Datenbanklink angezeigt, der auf das Remotepaket verweist.|  
|PLS_TYPE|Zeichenfolge|Der Name des PL/SQL-Typs des Arguments bei numerischen Argumenten. Andernfalls NULL.|  
|CHAR_LENGTH|Decimal|Zeichenbeschränkung für Daten des Typs string.|  
|CHAR_USED|Zeichenfolge|Gibt an, ob für die Zeichenfolge eine Bytebeschränkung (B) oder eine Zeichenbeschränkung (C) gilt.|  
  
## <a name="see-also"></a>Siehe auch  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
