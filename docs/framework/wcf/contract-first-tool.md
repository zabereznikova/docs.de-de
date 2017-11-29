---
title: Vertrag zuerst-Tool
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a880690-f460-4475-a5f4-9f91ce08fcc6
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea0821d9dd6073c1e652d36c71b817647b8710c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="contract-first-tool"></a>Vertrag zuerst-Tool
Dienstverträge müssen häufig aus vorhandenen Diensten erstellt werden. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] können Datenvertragsklassen mithilfe des Vertrag zuerst-Tools automatisch aus vorhandenen Diensten erstellt werden. Zum Verwenden des Vertrag zuerst-Tools muss die XSD (XML Schema Definition)-Datei lokal heruntergeladen werden. Das Tool kann keine Remotedatenverträge per HTTP importieren.  
  
 Das Vertrag zuerst-Tool ist als Buildaufgabe in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] integriert. Die von der Buildaufgabe generierten Codedateien werden bei jeder Projekterstellung erzeugt, sodass das Projekt einfach Änderungen im zugrunde liegenden Dienstvertrag übernehmen kann.  
  
 Folgende Schematypen können vom Vertrag zuerst-Tool importiert werden:  
  
```xml  
<xsd:complexType>  
<xsd:simpleType>  
```  
  
 Einfache Typen werden nicht generiert, wenn es sich um primitive Typen, z. B. `Int16` oder `String`, handelt. Komplexe Typen werden nicht generiert, wenn sie vom Typ `Collection` sind. Typen werden ebenfalls nicht generiert, wenn sie Teil eines anderen `xsd:complexType` sind. In allen diesen Fällen werden stattdessen Verweise dieser Typen auf im Projekt vorhandene Typen verwendet.  
  
## <a name="adding-a-data-contract-to-a-project"></a>Hinzufügen eines Datenvertrags zu einem Projekt  
 Bevor das Vertrag zuerst-Tool verwendet werden kann, muss dem Projekt der Dienstvertrag (XSD) hinzugefügt werden. In dieser Übersicht wird zum Veranschaulichen von Vertrag zuerst-Funktionen der folgende Vertrag verwendet. Diese Dienstdefinition ist eine kleine Teilmenge des Dienstvertrags, der von der Such-API von Bing verwendet wird.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="ServiceSchema"  
    targetNamespace="http://tempuri.org/ServiceSchema.xsd"  
    elementFormDefault="qualified"  
    xmlns="http://tempuri.org/ServiceSchema.xsd"  
    xmlns:mstns="http://tempuri.org/ServiceSchema.xsd"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema"  
>  
  <xs:complexType name="SearchRequest">  
    <xs:sequence>  
      <xs:element minOccurs="0" maxOccurs="1" name="Version" type="xs:string" default="2.2" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Market" type="xs:string" />  
      <xs:element minOccurs="0" maxOccurs="1" name="UILanguage" type="xs:string" />  
      <xs:element minOccurs="1" maxOccurs="1" name="Query" type="xs:string" />  
      <xs:element minOccurs="1" maxOccurs="1" name="AppId" type="xs:string" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Latitude" type="xs:double" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Longitude" type="xs:double" />  
      <xs:element minOccurs="0" maxOccurs="1" name="Radius" type="xs:double" />  
    </xs:sequence>  
  </xs:complexType>  
  <xs:simpleType name="WebSearchOption">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="DisableHostCollapsing" />  
      <xs:enumeration value="DisableQueryAlterations" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
 Um dem Projekt den obigen Dienstvertrag hinzufügen, mit der rechten Maustaste des Projekts, und wählen Sie **neue hinzufügen...** . Wählen Sie im WCF-Bereich des Dialogfelds Vorlagen die Schemadefinition aus, und benennen Sie die neue Datei mit SampleContract.xsd. Kopieren Sie den obigen Code, und fügen Sie ihn in die Codeansicht der neuen Datei ein.  
  
## <a name="configuring-contract-first-options"></a>Konfigurieren von Vertrag zuerst-Optionen  
 Vertrag zuerst-Optionen können im Eigenschaftenmenü eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Projekts konfiguriert werden. Um die Vertrag zuerst-Entwicklung aktivieren möchten, wählen Sie die **XSD als Typdefinitionssprache aktivieren** Kontrollkästchen in der WCF-Seite des Fensters Eigenschaften Projekt.  
  
 ![WCF-Projektoptionen mit Vertrag &#45; erste](../../../docs/framework/wcf/media/contractfirstoptions.png "ContractFirstOptions")  
  
 Um erweiterte Eigenschaften zu konfigurieren, klicken Sie auf die Schaltfläche Erweitert.  
  
 ![Erweiterte Vertrag &#45; Erste Eigenschaften](../../../docs/framework/wcf/media/contractfirstadvanced.png "ContractFirstAdvanced")  
  
 Die folgenden erweiterten Einstellungen können für die Codegenerierung aus Verträgen konfiguriert werden. Die Einstellungen können nur für alle Dateien im Projekt konfiguriert werden. Das Konfigurieren der Einstellungen für einzelne Dateien ist derzeit nicht möglich.  
  
-   **Serialisierungsmodus**: Diese Einstellung legt fest, welches Serialisierungsprogramm zum Lesen von Vertragsdateien verwendet wird. Wenn **XML-Serialisierungsprogramm** ausgewählt ist, die **Auflistungstypen** und **Typen wiederverwenden** Optionen sind deaktiviert. Diese Optionen gelten nur für die **Datenvertragsserialisierer**.  
  
-   **Typen wiederverwenden**: Diese Einstellung gibt an, welche Bibliotheken für die Wiederverwendung von Typen verwendet werden. Diese Einstellung gilt nur, wenn **Serialisierungsmodus** festgelegt ist, um **Datenvertragsserialisierer**.  
  
-   **"Sammlung"**: Diese Einstellung gibt den vollqualifizierten oder assemblyqualifizierten Typ für den Auflistungsdatentyp verwendet werden soll. Diese Einstellung gilt nur, wenn **Serialisierungsmodus** festgelegt ist, um **Datenvertragsserialisierer**.  
  
-   **Wörterbuchtyp**: Diese Einstellung gibt den vollqualifizierten oder assemblyqualifizierten Typ für den wörterbuchdatentyp verwendet werden soll.  
  
-   **EnableDataBinding**: Diese Einstellung gibt an, ob zum Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle für alle Datentypen, um die Datenbindung zu implementieren.  
  
-   **ExcludedTypes**: Diese Einstellung gibt die Liste der vollqualifizierten oder assemblyqualifizierten Typen aus der referenzierten Assemblys ausgeschlossen werden sollen. Diese Einstellung gilt nur, wenn **Serialisierungsmodus** festgelegt ist, um **Datenvertragsserialisierer**.  
  
-   **GenerateInternalTypes**: Diese Einstellung gibt an, ob Klassen generiert werden, die als intern markiert sind. Diese Einstellung gilt nur, wenn **Serialisierungsmodus** festgelegt ist, um **Datenvertragsserialisierer**.  
  
-   **GenerateSerializableTypes**: Diese Einstellung gibt an, ob zum Generieren von Klassen, mit der <xref:System.SerializableAttribute> Attribut. Diese Einstellung gilt nur, wenn **Serialisierungsmodus** festgelegt ist, um **Datenvertragsserialisierer**.  
  
-   **ImportXMLTypes**: Diese Einstellung gibt an, ob die Datenvertragsserialisierung so anwenden konfiguriert die <xref:System.SerializableAttribute> -Attribut auf Klassen ohne das <xref:System.Runtime.Serialization.DataContractAttribute> Attribut.  Diese Einstellung gilt nur, wenn **Serialisierungsmodus** festgelegt ist, um **Datenvertragsserialisierer**.  
  
-   **SupportFx35TypedDataSets**: Diese Einstellung gibt an, ob zusätzliche Funktionen für typisierte Datasets für .net erstellt bereitzustellen Framework 3.5. Wenn **Serialisierungsmodus** festgelegt ist, um **XML-Serialisierungsprogramm**, die <xref:System.Data.Design.TypedDataSetSchemaImporterExtensionFx35> Erweiterung wird an den XML-Schema-Importer hinzugefügt werden, wenn dieser Wert auf "true" festgelegt ist. Wenn **Serialisierungsmodus** festgelegt ist, um **Datenvertrags-Serialisierer**, den Typ <xref:System.DateTimeOffset> werden aus den Referenzen ausgeschlossen werden, wenn dieser Wert auf "false" festgelegt ist, damit eine <xref:System.DateTimeOffset> wird immer generiert Bei älteren Framework-Versionen.  
  
-   **InputXsdFiles**: Diese Einstellung gibt die Liste der Eingabedateien an. Jede Datei muss ein gültiges XML-Schema enthalten.  
  
-   **Sprache**: Diese Einstellung gibt die Sprache für den generierten Vertragscode. Die Einstellung muss vom <xref:System.CodeDom.Compiler.CodeDomProvider> erkannt werden können.  
  
-   **NamespaceMappings**: Diese Einstellung gibt an, das Zuordnungen aus der XSD-Zielnamespaces für CLR-Namespaces. Jede Zuordnung sollte folgendes Format aufweisen:  
  
    ```xml  
    "<Schema Namespace>, <CLR Namespace>"  
    ```  
  
     Die XML-Serialisierung akzeptiert nur eine Zuordnung im folgenden Format:  
  
    ```xml  
    "*, <CLR Namespace>"  
    ```  
  
-   **OutputDirectory**: Diese Einstellung gibt an, das Verzeichnis, in dem die Codedateien generiert werden.  
  
 Die Einstellungen werden verwendet, um Dienstvertragstypen aus Vertragsdateien zu generieren, wenn das Projekt erstellt wird.  
  
## <a name="using-contract-first-development"></a>Verwenden der Vertrag zuerst-Entwicklung  
 Nachdem das Projekt die Dienstvertrag hinzugefügt und die Buildeinstellungen bestätigt haben, erstellen Sie das Projekt durch Drücken von **F6**. Die Typen, die im Dienstvertrag definiert sind, stehen dann für die Verwendung im Projekt bereit.  
  
 Um die im Dienstvertrag definierten Typen zu verwenden, fügen Sie unter dem aktuellen Namespace einen Verweis auf `ContractTypes` hinzu:  
  
```csharp  
using MyProjectNamespace.ContractTypes;  
```  
  
 Die im Dienstvertrag definierten Typen sind dann wie unten dargestellt im Projekt auflösbar.  
  
 ![Verwenden von Typen aus einem Dienstvertrag abgeleitet](../../../docs/framework/wcf/media/contractfirsttypes.png "ContractFirstTypes")  
  
 Die vom Tool generierten Typen werden in der Datei GeneratedXSDTypes.cs erstellt. Die Datei wird erstellt, der \<Projektverzeichnis > /obj/\<Buildkonfiguration > /XSDGeneratedCode/ Directory standardmäßig. Das Beispielschema am Anfang dieses Themas wird wie folgt konvertiert:  
  
```csharp
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:4.0.30319.17330  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
namespace TestXSD3.ContractTypes  
{  
    using System.Xml.Serialization;  
  
    /// <remarks/>  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]  
    [System.SerializableAttribute()]  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.ComponentModel.DesignerCategoryAttribute("code")]  
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]  
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=true)]  
    public partial class SearchRequest  
    {  
  
        private string versionField;  
  
        private string marketField;  
  
        private string uILanguageField;  
  
        private string queryField;  
  
        private string appIdField;  
  
        private double latitudeField;  
  
        private bool latitudeFieldSpecified;  
  
        private double longitudeField;  
  
        private bool longitudeFieldSpecified;  
  
        private double radiusField;  
  
        private bool radiusFieldSpecified;  
  
        public SearchRequest()  
        {  
            this.versionField = "2.2";  
        }  
  
        /// <remarks/>  
        [System.ComponentModel.DefaultValueAttribute("2.2")]  
        public string Version  
        {  
            get  
            {  
                return this.versionField;  
            }  
            set  
            {  
                this.versionField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string Market  
        {  
            get  
            {  
                return this.marketField;  
            }  
            set  
            {  
                this.marketField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string UILanguage  
        {  
            get  
            {  
                return this.uILanguageField;  
            }  
            set  
            {  
                this.uILanguageField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string Query  
        {  
            get  
            {  
                return this.queryField;  
            }  
            set  
            {  
                this.queryField = value;  
            }  
        }  
  
        /// <remarks/>  
        public string AppId  
        {  
            get  
            {  
                return this.appIdField;  
            }  
            set  
            {  
                this.appIdField = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Latitude  
        {  
            get  
            {  
                return this.latitudeField;  
            }  
            set  
            {  
                this.latitudeField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool LatitudeSpecified  
        {  
            get  
            {  
                return this.latitudeFieldSpecified;  
            }  
            set  
            {  
                this.latitudeFieldSpecified = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Longitude  
        {  
            get  
            {  
                return this.longitudeField;  
            }  
            set  
            {  
                this.longitudeField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool LongitudeSpecified  
        {  
            get  
            {  
                return this.longitudeFieldSpecified;  
            }  
            set  
            {  
                this.longitudeFieldSpecified = value;  
            }  
        }  
  
        /// <remarks/>  
        public double Radius  
        {  
            get  
            {  
                return this.radiusField;  
            }  
            set  
            {  
                this.radiusField = value;  
            }  
        }  
  
        /// <remarks/>  
        [System.Xml.Serialization.XmlIgnoreAttribute()]  
        public bool RadiusSpecified  
        {  
            get  
            {  
                return this.radiusFieldSpecified;  
            }  
            set  
            {  
                this.radiusFieldSpecified = value;  
            }  
        }  
    }  
  
    /// <remarks/>  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Xml", "4.0.30319.17330")]  
    [System.SerializableAttribute()]  
    [System.Xml.Serialization.XmlTypeAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd")]  
    [System.Xml.Serialization.XmlRootAttribute(Namespace="http://tempuri.org/ServiceSchema.xsd", IsNullable=false)]  
    public enum WebSearchOption  
    {  
  
        /// <remarks/>  
        DisableHostCollapsing,  
  
        /// <remarks/>  
        DisableQueryAlterations,  
    }  
}  
```  
  
## <a name="errors-and-warnings"></a>Fehler und Warnungen  
 Fehler und Warnungen, die bei der Analyse des XSD-Schemas auftreten, werden als Buildfehler und Warnungen angezeigt.  
  
## <a name="interface-inheritance"></a>Schnittstellenvererbung  
 Bei der Vertrag zuerst-Entwicklung kann keine Schnittstellenvererbung verwendet werden. Dies entspricht dem Verhalten von Schnittstellen in anderen Vorgängen. Verwenden Sie für eine Schnittstelle, die eine Basisschnittstelle erbt, zwei verschiedene Endpunkte. Der erste Endpunkt verwendet den geerbten Vertrag, und der zweite Endpunkt implementiert die Basisschnittstelle.
