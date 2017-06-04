---
title: "Strukturierte Typen, die NULL-Werte zulassen (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)
Eine `null`\-Instanz eines strukturierten Typs ist eine Instanz, die nicht vorhanden ist.  Dies unterscheidet sich von einer vorhandenen Instanz, in der alle Eigenschaften den Wert `null` haben.  
  
 In diesem Thema werden strukturierte Typen beschrieben, die NULL\-Werte zulassen. Zu dieser Beschreibung gehören eine Aufzählung der Typen, die NULL\-Werte zulassen, und die Angabe von Codemustern, die `null`\-Instanzen von strukturierten Typen erstellen, die NULL\-Werte zulassen.  
  
## Arten strukturierter Typen, die NULL\-Werte zulassen  
 Es gibt drei Arten von Strukturtypen, die NULL\-Werte zulassen:  
  
-   Zeilentypen  
  
-   Komplexe Typen  
  
-   Entitätstypen  
  
## Codemuster, die NULL\-Instanzen strukturierter Typen erstellen  
 In den folgenden Szenarios werden `null`\-Instanzen erstellt:  
  
-   `null` als strukturierten Typ formen:  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   Umwandeln eines Basistyps in einen abgeleiteten Typ:  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   "Outer join on false"\-Bedingung:  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     \-\-oder  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     \-\-oder  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   Dereferenzierung eines `null`\-Verweises:  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   Abrufen von ANYELEMENT aus einer leeren Auflistung:  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   Überprüfen von Instanzen strukturierter Typen auf `null`:  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine(“[NULL]”);  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)