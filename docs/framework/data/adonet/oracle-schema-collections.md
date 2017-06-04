---
title: "Oracle-Schemaauflistungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 89a75de8-dee8-45e2-a97f-254d7e62e7e1
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Oracle-Schemaauflistungen
Der Microsoft .NET Framework\-Datenanbieter für Oracle unterstützt außer den allgemeinen Schemaauflistungen die folgenden spezifischen Schemaauflistungen:  
  
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
  
## Columns  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer der Tabelle, der Ansicht oder des Clusters.|  
|TABLE\_NAME|Zeichenfolge|Name der Tabelle, der Ansicht oder des Clusters.|  
|COLUMN\_NAME|Zeichenfolge|Spaltenname.|  
|ID|Decimal|Folgenummer der Spalte, nach Erstellung.|  
|Datentyp|Zeichenfolge|Datentyp der Spalte.|  
|LENGTH|Decimal|Länge der Spalte in Byte.|  
|PRECISION|Decimal|Decimal\-Genauigkeit für Datentyp NUMBER, binary\- Genauigkeit für Datentyp FLOAT, NULL für alle anderen Datentypen.|  
|SCALE|Decimal|Stellen rechts vom Dezimaltrennzeichen einer Zahl.|  
|NULLABLE|Zeichenfolge|Gibt an, ob NULL in einer Spalte zulässig ist.  Der Wert ist N, wenn für die Spalte eine NOT NULL\-Einschränkung vorliegt oder wenn die Spalte Teil eines PRIMARY KEY ist.|  
  
## Indexes  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer des Indexes|  
|INDEX\_NAME|Zeichenfolge|Name des Indexes.|  
|INDEX\_TYPE|Zeichenfolge|Typ des Indexes \(NORMAL, BITMAP, FUNCTION\-BASED NORMAL, FUNCTION\-BASED BITMAP oder DOMAIN\).|  
|TABLE\_OWNER|Zeichenfolge|Besitzer des Objekts im Index.|  
|TABLE\_NAME|Zeichenfolge|Name des Objekts im Index.|  
|TABLE\_TYPE|Zeichenfolge|Typ des Objekts im Index \(z. B. TABLE, CLUSTER\).|  
|UNIQUENESS|Zeichenfolge|Ob der Index UNIQUE oder NONUNIQUE ist.|  
|COMPRESSION|Zeichenfolge|Ob der Index ENABLED oder DISABLED ist.|  
|PREFIX\_LENGTH|Decimal|Anzahl der Spalten im Präfix des Komprimierungsschlüssels.|  
|TABLESPACE\_NAME|Zeichenfolge|Name des Tabellenbereichs, der den Index enthält.|  
|INI\_TRANS|Decimal|Ursprüngliche Anzahl von Transaktionen.|  
|MAX\_TRANS|Decimal|Maximale Anzahl von Transaktionen.|  
|INITIAL\_EXTENT|Decimal|Anfangsgröße des Bereichs.|  
|NEXT\_EXTENT|Decimal|Größe von Erweiterungsbereichen.|  
|MIN\_EXTENTS|Decimal|Minimale Anzahl von Erweiterungsbereichen im Segment.|  
|MAX\_EXTENTS|Decimal|Maximale Anzahl von Erweiterungsbereichen im Segment.|  
|PCT\_INCREASE|Decimal|Prozentuale Erhöhung der Größe des Erweiterungsbereichs.|  
|PCT\_THRESHOLD|Decimal|Prozentualer Schwellenwert des pro Indexeintag zulässigen Blockraums.|  
|INCLUDE\_COLUMN|Decimal|Spalten\-ID der letzten Spalte, die im Primärschlüsselindex \(ohne Überlauf\) einer nach dem Index sortierten Tabelle enthalten sein soll.  Diese Spalte wird der Spalte COLUMN\_ID der \*\_TAB\_COLUMNS\-Datenwörterbuchansichten zugeordnet.|  
|FREELISTS|Decimal|Anzahl von Prozess\-Freelists, die diesem Segment zugewiesen sind.|  
|FREELIST\_GROUPS|Decimal|Anzahl von Freelist\-Gruppen, die diesem Segment zugewiesen sind.|  
|PCT\_FREE|Decimal|Minimaler Prozentsatz des freien Speicherplatzes in einem Block.|  
|LOGGING|Zeichenfolge|Informationen zur Protokollierung.|  
|BLEVEL|Decimal|B\*\-Strukturebene: Tiefe des Indexes von dessen Stammblock bis zu seinem Endblock.  Eine Tiefe von 0 \(null\) gibt an, dass der Stammblock auch der Endblock ist.|  
|LEAF\_BLOCKS|Decimal|Anzahl von Endblöcken im Index.|  
|DISTINCT\_KEYS|Decimal|Anzahl der unterschiedlichen Werte im Index.  Bei Indizes, die die UNIQUE\-Einschränkung und die PRIMARY KEY\-Einschränkung erzwingen, entspricht dieser Wert der Anzahl von Zeilen in der Tabelle \(USER\_TABLES.NUM\_ROWS\).|  
|AVG\_LEAF\_BLOCKS\_PER\_KEY|Decimal|Durchschnittliche Anzahl von Endblöcken, wobei jeder unterschiedliche Wert im Index auf die nächste ganze Zahl gerundet angezeigt wird.  Bei Indizes, die die UNIQUE\-Eigenschaft und die PRIMARY KEY\-Eigenschaft erzwingen, ist dieser Wert immer 1.|  
|AVG\_DATA\_BLOCKS\_PER\_KEY|Decimal|Durchschnittliche Anzahl von Datenblöcken in der Tabelle, auf die im Index durch einen eindeutigen, auf die nächste ganze Zahl gerundeten Wert verwiesen wird.  Bei der Statistik handelt es sich um die durchschnittliche Anzahl von Datenblöcken mit Zeilen, die einen angegebenen Wert für die Spalten im Index enthalten.|  
|CLUSTERING\_FACTOR|Decimal|Gibt die Unregelmäßigkeit der Zeilen in der Tabelle anhand der Werte des Indexes an.|  
|STATUS|Zeichenfolge|Gibt an, ob ein nicht partitionierter Index VALID oder UNUSABLE ist.|  
|NUM\_ROWS|Decimal|Anzahl von Zeilen im Index.|  
|SAMPLE\_SIZE|Decimal|Größe des Beispiels, das zum Analysieren des Indexes verwendet wird.|  
|LAST\_ANALYZED|DateTime|Datum, an dem dieser Index zuletzt analysiert wurde.|  
|DEGREE|Zeichenfolge|Anzahl von Threads pro Instanz zum Durchsuchen des Indexes.|  
|INSTANCES|Zeichenfolge|Anzahl von Instanzen, in den die Indizes durchsucht werden sollen.|  
|PARTITIONED|Zeichenfolge|Gibt an, ob dieser Index partitioniert ist \(YES &#124; NO\).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob sich der Index in einer temporären Tabelle befindet.|  
|GENERATED|Zeichenfolge|Gibt an, ob der Name des Indexes vom System generiert wurde \(Y&#124;N\).|  
|SECONDARY|Zeichenfolge|Gibt an, ob es sich bei dem Index um ein sekundäres Objekt handelt, das von der ODCIIndexCreate\-Methode der Oracle9i Data Cartridge erstellt wurde \(Y&#124;N\).|  
|BUFFER\_POOL|Zeichenfolge|Name des Standardpufferpools, der für die Indexblöcke verwendet wird.|  
|USER\_STATS|Zeichenfolge|Gibt an, ob die Statistik direkt vom Benutzer eingegeben wurde.|  
|DURATION|Zeichenfolge|Gibt die Dauer einer temporären Tabelle an: 1\) SYS$SESSION: Die Zeilen werden für die Dauer der Sitzung beibehalten. 2\) SYS$TRANSACTION: Die Zeilen werden nach dem COMMIT gelöscht. 3\) NULL für eine dauerhafte Tabelle.|  
|PCT\_DIRECT\_ACCESS|Decimal|Der prozentuale Anteil von Reihen mit dem geschätzten Wert VALID bei einem sekundären Index in einer nach dem Index sortierten Tabelle|  
|ITYP\_OWNER|Zeichenfolge|Der Besitzer des Indextyps eines Domänenindexes.|  
|ITYP\_NAME|Zeichenfolge|Der Name des Indextyps eines Domänenindexes.|  
|PARAMETERS|Zeichenfolge|Die Parameterzeichenfolge eines Domänenindexes.|  
|GLOBAL\_STATS|Zeichenfolge|Gibt bei partitionierten Indizes an, ob Statistiken durch eine Analyse des gesamten Indexes erstellt wurden \(YES\) oder ob sie anhand von Statistiken zugrunde liegender Indexpartitionen und Unterpartitionen geschätzt wurden \(NO\).|  
|DOMIDX\_STATUS|Zeichenfolge|Gibt den Status des Domänenindexes an.  NULL: Bei dem angegebenen Index handelt es sich nicht um einen Domänenindex.  VALID: Bei dem Index handelt es sich um einen gültigen Domänenindex.  IDXTYP\_INVLD: Der Indextyp dieses Domänenindexes ist ungültig.|  
|DOMIDX\_OPSTATUS|Zeichenfolge|Gibt den Status eines Vorgangs an, der für einen Domänenindex durchgeführt wurde. NULL: Bei dem angegebenen Index handelt es sich nicht um einen Domänenindex.  VALID: Der Vorgang wurde fehlerfrei durchgeführt.  FAILED: Bei diesem Vorgang ist ein Fehler aufgetreten.|  
|FUNCIDX\_STATUS|Zeichenfolge|Gibt den Status eines funktionsbasierten Indexes an. NULL: Dies ist kein funktionsbasierter Index. ENABLED: Der funktionsbasierte Index ist aktiviert. DISABLED: Der funktionsbasierte Index ist deaktiviert.|  
|JOIN\_INDEX|Zeichenfolge|Gibt an, ob es sich hierbei um einen Joinindex handelt oder nicht.|  
  
## IndexColumns  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|INDEX\_OWNER|Zeichenfolge|Besitzer des Indexes.|  
|INDEX\_NAME|Zeichenfolge|Name des Indexes.|  
|TABLE\_OWNER|Zeichenfolge|Besitzer der Tabelle oder des Clusters.|  
|TABLE\_NAME|Zeichenfolge|Name der Tabelle oder des Clusters.|  
|COLUMN\_NAME|Zeichenfolge|Spaltenname oder Attribut der Objekttypspalte.|  
|COLUMN\_POSITION|Decimal|Position der Spalte oder des Attributs im Index.|  
|COLUMN\_LENGTH|Decimal|Länge der Spalte im Index.|  
|CHAR\_LENGTH|Decimal|Maximale Codepunktlänge der Spalte.|  
|DESCEND|Zeichenfolge|Gibt an, ob die Spalte in absteigender Reihenfolge sortiert wird.|  
  
## Verfahren  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT\_NAME|Zeichenfolge|Name des Objekts.|  
|SUBOBJECT\_NAME|Zeichenfolge|Name des Unterobjekts \(z. B. Partition\).|  
|OBJECT\_ID|Decimal|Wörterbuchobjektnummer des Objekts.|  
|DATA\_OBJECT\_ID|Decimal|Wörterbuchobjektnummer des Segments, in dem das Objekt enthalten ist.|  
|LAST\_DDL\_TIME|DateTime|Timestamp für die letzte Änderung des Objekts durch einen DDL\-Befehl \(einschließlich Gewährungen und Widerrufen\).|  
|TIMESTAMP|Zeichenfolge|Timestamp zur Spezifikation des Objekts \(Zeichendaten\).|  
|STATUS|Zeichenfolge|Status des Objekts \(VALID, INVALID oder N\/A\).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob das Objekt temporär ist \(von der aktuellen Sitzung können nur Daten angezeigt werden, die von ihr in diesem Objekt abgelegt wurden\).|  
|GENERATED|Zeichenfolge|Wurde der Name dieses Objekts vom System generiert?  \(Y &#124; N\).|  
|SECONDARY|Zeichenfolge|Gibt an, ob dies ein sekundäres Objekt ist, das von der ODCIIndexCreate\-Methode der Oracle9i Data Cartridge erstellt wurde \(Y &#124; N\).|  
|CREATED|DateTime|Das Datum, an dem das Objekt erstellt wurde.|  
  
## Sequenzen  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|SEQUENCE\_OWNER|Zeichenfolge|Name des Besitzers der Sequenz.|  
|SEQUENCE\_NAME|Zeichenfolge|Name der Sequenz.|  
|MIN\_VALUE|Decimal|Niedrigster Wert der Sequenz.|  
|MAX\_VALUE|Decimal|Höchster Wert der Sequenz.|  
|INCREMENT\_BY|Decimal|Wert, um den die Sequenz inkrementiert wird.|  
|CYCLE\_FLAG|Zeichenfolge|Führt Sequenz\-Wrapping beim Erreichen der Beschränkung aus.|  
|ORDER\_FLAG|Zeichenfolge|Sequenznummern werden der Reihe nach generiert.|  
|CACHE\_SIZE|Decimal|Anzahl der Sequenznummern, die zwischengespeichert werden soll.|  
|LAST\_NUMBER|Decimal|Letzte Sequenznummer, die auf den Datenträger geschrieben wird.  Wenn bei einer Sequenz die Zwischenspeicherung verwendet wird, wird die auf den Datenträger geschriebene Nummer zuletzt im Sequenzcache positioniert.  Diese Nummer ist wahrscheinlich größer als die zuletzt verwendete Sequenznummer.|  
  
## Synonyms  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer des Synonyms.|  
|SYNONYM\_NAME|Zeichenfolge|Name des Synonyms.|  
|TABLE\_OWNER|Zeichenfolge|Besitzer des Objekts, auf das das Synonym verweist.|  
|TABLE\_NAME|Zeichenfolge|Name des Objekts, auf das das Synonym verweist.|  
|DB\_LINK|Zeichenfolge|Name des ggf. vorhandenen Datenbanklinks, auf den verwiesen wird.|  
  
## Tabellen  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer der Tabelle.|  
|TABLE\_NAME|Zeichenfolge|Name der Tabelle.|  
|TYPE|Zeichenfolge|Tabellentyp.|  
  
## Benutzer  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|NAME|Zeichenfolge|Name des Benutzers.|  
|ID|Decimal|ID\-Nummer des Benutzers.|  
|CREATEDATE|DateTime|Datum der Benutzererstellung.|  
  
## Ansichten  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer der Ansicht.|  
|VIEW\_NAME|Zeichenfolge|Name der Ansicht.|  
|TEXT\_LENGTH|Decimal|Länge des Anzeigetexts.|  
|TEXT|Zeichenfolge|Anzeigetext.|  
|TYPE\_TEXT\_LENGTH|Decimal|Länge der Typklausel der typisierten Ansicht.|  
|TYPE\_TEXT|Zeichenfolge|Typklausel der typisierten Ansicht.|  
|OID\_TEXT\_LENGTH|Decimal|Länge der **WITH OID**\-Klausel der typisierten Ansicht.|  
|OID\_TEXT|Zeichenfolge|WITH OID\-Klausel der typisierten Ansicht.|  
|VIEW\_TYPE\_OWNER|Zeichenfolge|Besitzer des Typs der Ansicht, wenn es sich bei der Ansicht um eine typisierte Ansicht handelt.|  
|VIEW\_TYPE|Zeichenfolge|Typ der Ansicht, wenn es sich bei der Ansicht um eine typisierte Ansicht handelt.|  
|SUPERVIEW\_NAME|Zeichenfolge|Name der Überblicksansicht.|  
  
## Funktionen  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT\_NAME|Zeichenfolge|Name des Objekts.|  
|SUBOBJECT\_NAME|Zeichenfolge|Name des Unterobjekts \(z. B. Partition\).|  
|OBJECT\_ID|Decimal|Wörterbuchobjektnummer des Objekts.|  
|DATA\_OBJECT\_ID|Decimal|Wörterbuchobjektnummer des Segments, in dem das Objekt enthalten ist.|  
|OBJECT\_TYPE|Zeichenfolge|Typ des Objekts.|  
|CREATED|DateTime|Das Datum, an dem das Objekt erstellt wurde.|  
|LAST\_DDL\_TIME|DateTime|Timestamp für die letzte Änderung des Objekts durch einen DDL\-Befehl \(einschließlich Gewährungen und Widerrufen\).|  
|TIMESTAMP|Zeichenfolge|Timestamp zur Spezifikation des Objekts \(Zeichendaten\).|  
|STATUS|Zeichenfolge|Status des Objekts \(VALID, INVALID oder N\/A\).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob das Objekt temporär ist \(von der aktuellen Sitzung können nur Daten angezeigt werden, die von ihr in diesem Objekt abgelegt wurden\).|  
|GENERATED|Zeichenfolge|Wurde der Name dieses Objekts vom System generiert?  \(Y &#124; N\).|  
|SECONDARY|Zeichenfolge|Gibt an, ob dies ein sekundäres Objekt ist, das von der ODCIIndexCreate\-Methode der Oracle9i Data Cartridge erstellt wurde \(Y &#124; N\).|  
  
## Pakete  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT\_NAME|Zeichenfolge|Name des Objekts.|  
|SUBOBJECT\_NAME|Zeichenfolge|Name des Unterobjekts \(z. B. Partition\).|  
|OBJECT\_ID|Decimal|Wörterbuchobjektnummer des Objekts.|  
|DATA\_OBJECT\_ID|Decimal|Wörterbuchobjektnummer des Segments, in dem das Objekt enthalten ist.|  
|LAST\_DDL\_TIME|DateTime|Timestamp für die letzte Änderung des Objekts durch einen DDL\-Befehl \(einschließlich Gewährungen und Widerrufen\).|  
|TIMESTAMP|Zeichenfolge|Timestamp zur Spezifikation des Objekts \(Zeichendaten\).|  
|STATUS|Zeichenfolge|Status des Objekts \(VALID, INVALID oder N\/A\).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob das Objekt temporär ist \(von der aktuellen Sitzung können nur Daten angezeigt werden, die von ihr in diesem Objekt abgelegt wurden\).|  
|GENERATED|Zeichenfolge|Wurde der Name dieses Objekts vom System generiert?  \(Y &#124; N\).|  
|SECONDARY|Zeichenfolge|Gibt an, ob dies ein sekundäres Objekt ist, das von der ODCIIndexCreate\-Methode der Oracle9i Data Cartridge erstellt wurde \(Y &#124; N\).|  
|CREATED|DateTime|Das Datum, an dem das Objekt erstellt wurde.|  
  
## PackageBodies  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT\_NAME|Zeichenfolge|Name des Objekts.|  
|SUBOBJECT\_NAME|Zeichenfolge|Name des Unterobjekts \(z. B. Partition\).|  
|OBJECT\_ID|Decimal|Wörterbuchobjektnummer des Objekts.|  
|DATA\_OBJECT\_ID|Decimal|Wörterbuchobjektnummer des Segments, in dem das Objekt enthalten ist.|  
|LAST\_DDL\_TIME|DateTime|Timestamp für die letzte Änderung des Objekts durch einen DDL\-Befehl \(einschließlich Gewährungen und Widerrufen\).|  
|TIMESTAMP|Zeichenfolge|Timestamp zur Spezifikation des Objekts \(Zeichendaten\).|  
|STATUS|Zeichenfolge|Status des Objekts \(VALID, INVALID oder N\/A\).|  
|TEMPORARY|Zeichenfolge|Gibt an, ob das Objekt temporär ist \(von der aktuellen Sitzung können nur Daten angezeigt werden, die von ihr in diesem Objekt abgelegt wurden\).|  
|GENERATED|Zeichenfolge|Wurde der Name dieses Objekts vom System generiert?  \(Y &#124; N\).|  
|SECONDARY|Zeichenfolge|Gibt an, ob dies ein sekundäres Objekt ist, das von der ODCIIndexCreate\-Methode der Oracle9i Data Cartridge erstellt wurde \(Y &#124; N\).|  
|CREATED|DateTime|Das Datum, an dem das Objekt erstellt wurde.|  
  
## Argumente  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Name des Besitzers des Objekts.|  
|PACKAGE\_NAME|Zeichenfolge|Name des Pakets.|  
|OBJECT\_NAME|Zeichenfolge|Name der Prozedur oder Funktion.|  
|ARGUMENT\_NAME|Zeichenfolge|Name des Arguments.|  
|POSITION|Decimal|Position in der Argumentliste oder NULL für den Rückgabewert einer Funktion.|  
|SEQUENCE|Decimal|Argumentsequenz einschließlich aller geschachtelten Ebenen.|  
|DEFAULT\_VALUE|Zeichenfolge|Standardwert für das Argument.|  
|DEFAULT\_LENGTH|Decimal|Länge des Standardwerts für das Argument.|  
|IN\_OUT|Zeichenfolge|Argumentrichtung \(IN, OUT oder IN\/OUT\).|  
|DATA\_LENGTH|Decimal|Länge der Spalte in Byte.|  
|DATA\_PRECISION|Decimal|Länge in Dezimalstellen \(NUMBER\) oder Binärzahlen \(FLOAT\).|  
|DATA\_SCALE|Decimal|Stellen rechts vom Dezimaltrennzeichen einer Zahl.|  
|DATA\_TYPE|Zeichenfolge|Datentyp des Arguments.|  
  
## UniqueKeys  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|CONSTRAINT\_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|TABLE\_NAME|Zeichenfolge|Name, der der Tabelle \(oder Ansicht\) mit der Einschränkungsdefinition zugeordnet ist.|  
|SEARCH\_CONDITION|Zeichenfolge|Text der Suchbedingung für eine CHECK\-Einschränkung.|  
|R\_OWNER|Zeichenfolge|Besitzer einer Tabelle, auf die in einer referenziellen Einschränkung verwiesen wird.|  
|R\_CONSTRAINT\_NAME|Zeichenfolge|Name der Definition der UNIQUE\-Einschränkung für die Tabelle, auf die verwiesen wird.|  
|DELETE\_RULE|Zeichenfolge|Löschregel für eine referenzielle Einschränkung \(CASCADE oder NO ACTION\).|  
|STATUS|Zeichenfolge|Erzwingungsstatus einer Einschränkung \(ENABLED oder DISABLED\).|  
|DEFERRABLE|Zeichenfolge|Gibt an, ob die Einschränkung verzögert werden kann.|  
|VALIDATED|Zeichenfolge|Gibt an, ob die Einschränkung bei allen Daten berücksichtigt wird \(VALIDATED oder NOT VALIDATED\).|  
|GENERATED|Zeichenfolge|Gibt an, ob der Name einer Einschränkung vom Benutzer oder vom System generiert wurde.|  
|BAD|Zeichenfolge|Der Wert YES gibt an, dass diese Einschränkung ein Jahrhundert nicht eindeutig angibt.  Um aufgrund dieser Mehrdeutigkeit entstehende Fehler zu vermeiden, schreiben Sie die Einschränkung mithilfe der TO\_DATE\-Funktion mit einer vierstelligen Jahreszahl neu.|  
|RELY|Zeichenfolge|Gibt an, ob eine aktivierte Einschränkung erzwungen oder nicht erzwungen ist.|  
|LAST\_CHANGE|DateTime|Gibt an, wann die Einschränkung zuletzt aktiviert oder deaktiviert wurde.|  
|INDEX\_OWNER|Zeichenfolge|Name des Benutzers, dem der Index gehört.|  
|INDEX\_NAME|Zeichenfolge|Name des Indexes.|  
  
## PrimaryKeys  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|CONSTRAINT\_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|TABLE\_NAME|Zeichenfolge|Name, der der Tabelle \(oder Ansicht\) mit der Einschränkungsdefinition zugeordnet ist.|  
|SEARCH\_CONDITION|Zeichenfolge|Text der Suchbedingung für eine CHECK\-Einschränkung.|  
|R\_OWNER|Zeichenfolge|Besitzer einer Tabelle, auf die in einer referenziellen Einschränkung verwiesen wird.|  
|R\_CONSTRAINT\_NAME|Zeichenfolge|Name der Definition der UNIQUE\-Einschränkung für die Tabelle, auf die verwiesen wird.|  
|DELETE\_RULE|Zeichenfolge|Löschregel für eine referenzielle Einschränkung \(CASCADE oder NO ACTION\).|  
|STATUS|Zeichenfolge|Erzwingungsstatus einer Einschränkung \(ENABLED oder DISABLED\).|  
|DEFERRABLE|Zeichenfolge|Gibt an, ob die Einschränkung verzögert werden kann.|  
|VALIDATED|Zeichenfolge|Gibt an, ob die Einschränkung bei allen Daten berücksichtigt wird \(VALIDATED oder NOT VALIDATED\).|  
|GENERATED|Zeichenfolge|Gibt an, ob der Name einer Einschränkung vom Benutzer oder vom System generiert wurde.|  
|BAD|Zeichenfolge|Der Wert YES gibt an, dass diese Einschränkung ein Jahrhundert nicht eindeutig angibt.  Um aufgrund dieser Mehrdeutigkeit entstehende Fehler zu vermeiden, schreiben Sie die Einschränkung mithilfe der TO\_DATE\-Funktion mit einer vierstelligen Jahreszahl neu.|  
|RELY|Zeichenfolge|Gibt an, ob eine aktivierte Einschränkung erzwungen oder nicht erzwungen ist.|  
|LAST\_CHANGE|DateTime|Gibt an, wann die Einschränkung zuletzt aktiviert oder deaktiviert wurde.|  
|INDEX\_OWNER|Zeichenfolge|Name des Benutzers, dem der Index gehört.|  
|INDEX\_NAME|Zeichenfolge|Name des Indexes.|  
  
## ForeignKeys  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|PRIMARY\_KEY\_CONSTRAINT\_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|PRIMARY\_KEY\_OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|PRIMARY\_KEY\_TABLE\_NAME|Zeichenfolge|Name, der der Tabelle \(oder Ansicht\) mit der Einschränkungsdefinition zugeordnet ist.|  
|FOREIGN\_KEY\_OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|FOREIGN\_KEY\_CONSTRIANT\_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|FOREIGN\_KEY\_TABLE\_NAME|Zeichenfolge|Name, der der Tabelle \(oder Ansicht\) mit der Einschränkungsdefinition zugeordnet ist.|  
|SEARCH\_CONDITION|Zeichenfolge|Text der Suchbedingung für eine CHECK\-Einschränkung.|  
|R\_OWNER|Zeichenfolge|Besitzer einer Tabelle, auf die in einer referenziellen Einschränkung verwiesen wird.|  
|R\_CONSTRAINT\_NAME|Zeichenfolge|Name der Definition der UNIQUE\-Einschränkung für die Tabelle, auf die verwiesen wird.|  
|DELETE\_RULE|Zeichenfolge|Löschregel für eine referenzielle Einschränkung \(CASCADE oder NO ACTION\).|  
|STATUS|Zeichenfolge|Erzwingungsstatus einer Einschränkung \(ENABLED oder DISABLED\).|  
|VALIDATED|Zeichenfolge|Gibt an, ob die Einschränkung bei allen Daten berücksichtigt wird \(VALIDATED oder NOT VALIDATED\).|  
|GENERATED|Zeichenfolge|Gibt an, ob der Name einer Einschränkung vom Benutzer oder vom System generiert wurde.|  
|RELY|Zeichenfolge|Gibt an, ob eine aktivierte Einschränkung erzwungen oder nicht erzwungen ist.|  
|LAST\_CHANGE|DateTime|Gibt an, wann die Einschränkung zuletzt aktiviert oder deaktiviert wurde.|  
|INDEX\_OWNER|Zeichenfolge|Name des Benutzers, dem der Index gehört.|  
|INDEX\_NAME|Zeichenfolge|Name des Indexes.|  
  
## ForeignKeyColumns  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer der Einschränkungsdefinition.|  
|CONSTRAINT\_NAME|Zeichenfolge|Name der Einschränkungsdefinition.|  
|TABLE\_NAME|Zeichenfolge|Name der Tabelle mit der Einschränkungsdefinition.|  
|COLUMN\_NAME|Zeichenfolge|Name der Spalte oder des Attributs der Objekttypspalte, die in der Einschränkungsdefinition angegeben ist.|  
|POSITION|Decimal|Ursprüngliche Position der Spalte oder des Attributs in der Definition des Objekts.|  
  
## ProcedureParameters  
  
|Spaltenname|DataType|Beschreibung|  
|-----------------|--------------|------------------|  
|OWNER|Zeichenfolge|Besitzer des Objekts.|  
|OBJECT\_NAME|Zeichenfolge|Name der Prozedur oder Funktion.|  
|PACKAGE\_NAME|Zeichenfolge|Name der Prozedur oder Funktion.|  
|OBJECT\_ID|Decimal|Objektnummer des Objekts.|  
|OVERLOAD|Zeichenfolge|Eindeutiger Bezeichner bei Überladungen.|  
|ARGUMENT\_NAME|Zeichenfolge|Name des Arguments.|  
|POSITION|Decimal|Position in der Argumentliste oder NULL für den Rückgabewert einer Funktion.|  
|SEQUENCE|Decimal|Argumentsequenz einschließlich aller geschachtelten Ebenen.|  
|DATA\_LEVEL|Decimal|Schachtelungstiefe des Arguments für zusammengesetzte Typen.|  
|DATA\_TYPE|Zeichenfolge|Datentyp des Arguments.|  
|DEFAULT\_VALUE|Zeichenfolge|Standardwert für das Argument.|  
|DEFAULT\_LENGTH|Decimal|Länge des Standardwerts für das Argument.|  
|IN\_OUT|Zeichenfolge|Argumentrichtung \(IN, OUT oder IN\/OUT\).|  
|DATA\_LENGTH|Decimal|Länge der Spalten \(in Byte\).|  
|DATA\_PRECISION|Decimal|Länge in Dezimalstellen \(NUMBER\) oder Binärzahlen \(FLOAT\).|  
|DATA\_SCALE|Decimal|Stellen rechts vom Dezimaltrennzeichen einer Zahl.|  
|RADIX|Decimal|Argumentbasis für eine Zahl.|  
|CHARACTER\_SET\_NAME|Zeichenfolge|Name des Zeichensatzes für das Argument.|  
|TYPE\_OWNER|Zeichenfolge|Besitzer des Argumenttyps.|  
|TYPE\_NAME|Zeichenfolge|Name des Argumenttyps.  Wenn es sich bei dem Typ um einen im Paket befindlichen lokalen Typ handelt \(d. h. er ist in einer Paketspezifikation deklariert\), wird in dieser Spalte der Name des Pakets angezeigt.|  
|TYPE\_SUBNAME|Zeichenfolge|Nur bei im Paket befindlichen lokalen Typen relevant.  Zeigt den Namen des Typs an, der im in der Spalte TYPE\_NAME angegebenen Paket deklariert ist.|  
|TYPE\_LINK|Zeichenfolge|Nur bei im Paket befindlichen lokalen Typen relevant, wenn es sich bei dem in der Spalte TYPE\_NAME angegebenen Paket um ein Remotepaket handelt.  In dieser Spalte wird der Datenbanklink angezeigt, der auf das Remotepaket verweist.|  
|PLS\_TYPE|Zeichenfolge|Der Name des PL\/SQL\-Typs des Arguments bei numerischen Argumenten.  Andernfalls NULL.|  
|CHAR\_LENGTH|Decimal|Zeichenbeschränkung für Daten des Typs string.|  
|CHAR\_USED|Zeichenfolge|Gibt an, ob für die Zeichenfolge eine Bytebeschränkung \(B\) oder eine Zeichenbeschränkung \(C\) gilt.|  
  
## Siehe auch  
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)