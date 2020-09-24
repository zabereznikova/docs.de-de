---
title: Entity SQL-Kurzreferenz
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: 7ec3b6fc184b4f169d6f6489bda0ec8fa4abb4f5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148139"
---
# <a name="entity-sql-quick-reference"></a>Entity SQL-Kurzreferenz

Dieses Thema enthält eine Kurzreferenz zu [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Abfragen. Die Abfragen in diesem Thema basieren auf dem AdventureWorks Sales-Modell.  
  
## <a name="literals"></a>Literale  
  
### <a name="string"></a>String  

 Es gibt Zeichenfolgenliterale, die aus Unicode-, und solche, die aus Nicht-Unicode-Zeichen bestehen. Unicode-Zeichen folgen wird N vorangesteht. Beispiel: `N'hello'` .  
  
 Im Folgenden ist ein Beispiel für ein nicht-Unicode-Zeichenfolgenliteral abgebildet:  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 Ausgabe:  
  
|Wert|  
|-----------|  
|Hello|  
  
### <a name="datetime"></a>Datetime  

 In DateTime-Literalen sind sowohl das Datum als auch die Uhrzeit erforderlich. Es gibt keine Standardwerte.  
  
 Beispiel:  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 Ausgabe:  
  
|Wert|  
|-----------|  
|12/25/2006 1:01:00 AM|  
  
### <a name="integer"></a>Integer  

 Ganzzahlige Literale können vom Typ Int32 (123), UInt32 (123U), Int64 (123L) und UInt64 (123UL) sein.  
  
 Beispiel:  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 Ausgabe:  
  
|Wert|  
|-----------|  
|1|  
|2|  
|3|  
  
### <a name="other"></a>Andere  

 Andere von  unterstützte Literale sind Guid, Binary, Float/Double, Decimal und . NULL-Literale werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] als mit allen anderen Typen im kozeptionellen Modell kompatibel aufgefasst.  
  
## <a name="type-constructors"></a>Typkonstruktoren  
  
### <a name="row"></a>ROW  

 [Row](row-entity-sql.md) erstellt einen anonymen, strukturell typisierten (Datensatz-) Wert wie in: `ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 Beispiel:  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 Ausgabe:  
  
|ProductID|Name|  
|---------------|----------|  
|1|Adjustable Race|  
|879|All-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### <a name="multiset"></a>MULTISET  

 [Multiset](multiset-entity-sql.md) -Konstrukte, wie z. b.:  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 Beispiel:  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 Ausgabe:  
  
|ProductID|Name|ProductNumber|…|  
|---------------|----------|-------------------|-------|  
|842|Touring-Panniers, Large|PA-T100|…|  
  
### <a name="object"></a>Object  

 [Konstruktorkonstrukte benannter Typen](named-type-constructor-entity-sql.md) (benannte) benutzerdefinierte Objekte, z `person("abc", 12)` . b..  
  
 Beispiel:  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 Ausgabe:  
  
|SalesOrderDetailID|CarrierTrackingNumber|OrderQty|ProductID|...|  
|------------------------|---------------------------|--------------|---------------|---------|  
|1|4911-403C-98|1|776|...|  
|2|4911-403C-98|3|777|...|  
|...|...|...|...|...|  
  
## <a name="references"></a>References  
  
### <a name="ref"></a>REF  

 [Ref](ref-entity-sql.md) erstellt einen Verweis auf eine Entitätstyp Instanz. Die folgende Abfrage gibt beispielsweise einen Verweis auf jede Order-Entität in der Orders-Entitätenmenge zurück:  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 Ausgabe:  
  
|Wert|  
|-----------|  
|1|  
|2|  
|3|  
|...|  
  
 Im folgenden Beispiel wird der Eigenschaftsextrahierungsoperator (.) für den Zugriff auf eine Eigenschaft einer Entität verwendet. Bei der Verwendung des Eigenschaftsextraktionsoperators wird der Verweis automatisch dereferenziert.  
  
 Beispiel:  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 Ausgabe:  
  
|Wert|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="deref"></a>DEREF  

 [Deref](deref-entity-sql.md) dereferenziert einen Verweis Wert und erstellt das Ergebnis dieser Dereferenzierung. Die folgende Abfrage erstellt beispielsweise die Order-Entitäten für jede Bestellung in der Orders-Entitätenmenge: `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2`.  
  
 Beispiel:  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 Ausgabe:  
  
|Wert|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="createref-and-key"></a>CREATEREF UND KEY  

 " [Kreateref](createref-entity-sql.md) " erstellt einen Verweis, der einen Schlüssel übergibt. [Key](key-entity-sql.md) extrahiert den Schlüsselteil eines Ausdrucks mit Typverweis.  
  
 Beispiel:  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 Ausgabe:  
  
|ProductID|  
|---------------|  
|980|  
|365|  
|771|  
|...|  
  
## <a name="functions"></a>Functions  
  
### <a name="canonical"></a>Canonical  

 Der Namespace für [kanonische Funktionen](canonical-functions.md) ist EDM, wie in `Edm.Length("string")` . Der Namespace muss nur dann angegeben werden, wenn ein anderer Namespace importiert wurde, der eine Funktion mit dem gleichen Namen wie eine kanonische Funktion enthält. Wenn zwei Namespaces über die gleiche Funktion verfügen, sollte der Benutzer den vollständigen Namen angeben.  
  
 Beispiel:  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 Ausgabe:  
  
|NameLen|  
|-------------|  
|6|  
|6|  
|5|  
  
### <a name="microsoft-provider-specific"></a>Microsoft-anbieterspezifische Funktionen  

 [Microsoft-anbieterspezifische Funktionen](../sqlclient-for-ef-functions.md) befinden sich im- `SqlServer` Namespace.  
  
 Beispiel:  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 Ausgabe:  
  
|EmailLen|  
|--------------|  
|27|  
|27|  
|26|  
  
## <a name="namespaces"></a>Namespaces  

 Die [Verwendung](using-entity-sql.md) von gibt in einem Abfrage Ausdruck verwendete Namespaces an.  
  
 Beispiel:  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 Ausgabe:  
  
|Wert|  
|-----------|  
|aa|  
  
## <a name="paging"></a>Paging  

 Paging kann ausgedrückt werden, indem Sie eine [Skip](skip-entity-sql.md) -und [Limit](limit-entity-sql.md) -Unterklausel in der [Order by](order-by-entity-sql.md) -Klausel deklarieren.  
  
 Beispiel:  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 Ausgabe:  
  
|id|Name|  
|--------|----------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## <a name="grouping"></a>Gruppierung  

 [Gruppieren nach](group-by-entity-sql.md) gibt Gruppen an, in die von einem Abfrage Ausdruck ([Select](select-entity-sql.md)) zurückgegebene Objekte eingefügt werden sollen.  
  
 Beispiel:  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 Ausgabe:  
  
|name|  
|----------|  
|LL Mountain Seat Assembly|  
|ML Mountain Seat Assembly|  
|HL Mountain Seat Assembly|  
|...|  
  
## <a name="navigation"></a>Navigation  

 Der Beziehungsnavigationsoperator ermöglicht die Navigation der Beziehung von einer Entität (an einem Ende) zu einer anderen Entität (am anderen Ende). [Navigate](navigate-entity-sql.md) übernimmt den Beziehungstyp als \<namespace> . \<relationship type name> Navigate gibt Ref zurück \<T> , wenn die Kardinalität des "to"-Endes "1" ist. Wenn die Kardinalität des "to"-Endes "n" ist, wird die Auflistung<Ref \<T>> zurückgegeben.  
  
 Beispiel:  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 Ausgabe:  
  
|AddressID|  
|---------------|  
|1|  
|2|  
|3|  
|...|  
  
## <a name="select-value-and-select"></a>SELECT VALUE UND SELECT  
  
### <a name="select-value"></a>SELECT VALUE  

  stellt die SELECT VALUE-Klausel bereit, um die implizite Zeilenkonstruktion zu überspringen. In einer SELECT VALUE-Klausel kann nur ein Element angegeben werden. Wenn eine solche Klausel verwendet wird, wird kein Zeilen Wrapper um die Elemente in der SELECT-Klausel erstellt, und eine Auflistung der gewünschten Form kann erstellt werden, z. b `SELECT VALUE a` .:.  
  
 Beispiel:  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 Ausgabe:  
  
|Name|  
|----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="select"></a>SELECT  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt auch den Zeilenkonstruktor zum Erstellen beliebiger Zeilen bereit. SELECT werden ein oder mehrere Elemente in der Projektion übergeben, und das Ergebnis ist ein Datensatz mit Feldern, z. B.: .  
  
 Beispiel:  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p Ausgabe:  
  
|Name|ProductID|  
|----------|---------------|  
|Adjustable Race|1|  
|All-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## <a name="case-expression"></a>CASE EXPRESSION  

 Der [Case-Ausdruck](case-entity-sql.md) wertet eine Reihe von booleschen Ausdrücken aus, um das Ergebnis zu bestimmen.  
  
 Beispiel:  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 Ausgabe:  
  
|Wert|  
|-----------|  
|TRUE|  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
