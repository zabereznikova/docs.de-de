---
title: "Oracle-Datentypzuordnungen | Microsoft Docs"
ms.custom: ""
ms.date: "02/15/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d2521bcc-0051-4f35-8be3-e8723edeaf6f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
---
# Oracle-Datentypzuordnungen
In der folgenden Tabelle ist der hergeleitete [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ für Datentypen vom .NET Framework\-Datenanbieter für Oracle \(<xref:System.Data.OracleClient>\) dargestellt. Außerdem werden die typisierten Accessormethoden für den <xref:System.Data.OracleClient.OracleDataReader> aufgeführt.  
  
|Oracle\-Typ|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ|Typisierter [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Accessor|Typisierter OracleType\-Accessor|  
|-----------------|----------------------------------------------------------------------|---------------------------------------------------------------------------------------|--------------------------------------|  
|BFILE|Byte\[\]|GetBytes\(\)|GetOracleBFile\(\)|  
|BLOB|Byte\[\]|GetBytes\(\)|GetOracleLob\(\)|  
|CHAR|Zeichenfolge<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|CLOB|Zeichenfolge<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|DATE|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|FLOAT|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTEGER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|INTERVAL YEAR TO MONTH \*|Int32|GetInt32\(\)|GetOracleMonthSpan\(\)|  
|INTERVAL DAY TO SECOND \*|TimeSpan|GetTimeSpan\(\)|GetOracleTimeSpan\(\)|  
|LONG|Zeichenfolge<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|LONG RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|NCHAR|Zeichenfolge<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|NCLOB|Zeichenfolge<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleLob\(\)|  
|NUMBER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|NVARCHAR2|Zeichenfolge<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|RAW|Byte\[\]|GetBytes\(\)|GetOracleBinary\(\)|  
|REF CURSOR||||  
|ROWID|Zeichenfolge<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
|TIMESTAMP \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH LOCAL TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|TIMESTAMP WITH TIME ZONE \*|DateTime|GetDateTime\(\)|GetOracleDateTime\(\)|  
|UNSIGNED INTEGER|Decimal|GetDecimal\(\)|GetOracleNumber\(\) \*\*|  
|VARCHAR2|Zeichenfolge<br /><br /> Char\[\]|GetString\(\)<br /><br /> GetChars\(\)|GetOracleString\(\)|  
  
 \* Der angegebene Oracle\-Typ ist nur verfügbar, wenn die Oracle 9i\-Software sowohl für den Client als auch für den Server verwendet wird.  
  
 \*\* Der Oracle\-Typ NUMBER darf aus maximal 38 signifikanten Ziffern bestehen. Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ von `decimal` ist auf 28 Ziffern begrenzt. Wenn der Oracle\-Typ NUMBER in einen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Typ von `decimal` eingelesen wird und der NUMBER\-Wert aus mehr als 28 Ziffern besteht, wird eine `OverflowException` ausgelöst. Wenn Sie einen Wert des Oracle\-Typs NUMBER aus dem `OracleDataReader` einlesen, wird empfohlen, die typisierte `GetOracleNumber`\-Accessormethode aufzurufen, um solche Werte als `OracleNumber` zurückzugeben. Beim Füllen eines `DataSet` können Sie mit dem `FillError`\-Ereignis ermitteln, ob eine `OverflowException` aufgetreten ist und ggf. entsprechende Maßnahmen ergreifen. Weitere Informationen zum `FillError`\-Ereignis finden Sie unter [Umgang mit 'DataAdapter'\-Ereignissen](../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## Siehe auch  
 [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)   
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)