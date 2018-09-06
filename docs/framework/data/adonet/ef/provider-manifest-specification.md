---
title: Anbietermanifestspezifikation
ms.date: 03/30/2017
ms.assetid: bb450b47-8951-4f99-9350-26f05a4d4e46
ms.openlocfilehash: 9875f0ce8d7b10532d7545c05d58ab43146120f0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739272"
---
# <a name="provider-manifest-specification"></a><span data-ttu-id="953ae-102">Anbietermanifestspezifikation</span><span class="sxs-lookup"><span data-stu-id="953ae-102">Provider Manifest Specification</span></span>
<span data-ttu-id="953ae-103">In diesem Abschnitt wird erläutert, wie ein Datenspeicheranbieter die Typen und Funktionen im Datenspeicher unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="953ae-103">This section discusses how a data store provider can support the types and functions in the data store.</span></span>  
  
 <span data-ttu-id="953ae-104">Entitätsdienste werden unabhängig von einem bestimmten Datenspeicheranbieter ausgeführt. Datenanbieter können jedoch explizit definieren, wie Modelle, Zuordnungen und Abfragen mit einem zugrunde liegenden Datenspeicher interagieren.</span><span class="sxs-lookup"><span data-stu-id="953ae-104">Entity Services operates independently of a specific data store provider yet still allows a data provider to explicitly define how models, mappings, and queries interact with an underlying data store.</span></span> <span data-ttu-id="953ae-105">Ohne eine Abstraktionsebene zielen Entitätsdienste lediglich auf einen bestimmten Datenspeicher oder einen Datenanbieter ab.</span><span class="sxs-lookup"><span data-stu-id="953ae-105">Without a layer of abstraction, Entity Services could only be targeted at a specific data store or data provider.</span></span>  
  
 <span data-ttu-id="953ae-106">Vom Anbieter unterstützte Typen werden direkt oder indirekt von der zugrunde liegende Datenbank unterstützt.</span><span class="sxs-lookup"><span data-stu-id="953ae-106">Types that the provider supports are directly or indirectly supported by the underlying database.</span></span> <span data-ttu-id="953ae-107">Bei diesen Typen muss es sich nicht unbedingt um die genauen Speichertypen handeln, sondern um die Typen, die der Anbieter für die Unterstützung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="953ae-107">These types are not necessarily the exact store types, but the types the provider uses to support the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="953ae-108">Anbieter-/Speichertypen werden mit den EDM (Entity Data Model)-Begriffen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="953ae-108">Provider/store types are described in the Entity Data Model (EDM) terms.</span></span>  
  
 <span data-ttu-id="953ae-109">Die Parameter und Rückgabetypen für die vom Datenspeicher unterstützten Funktionen werden in EDM-Begriffen angegeben.</span><span class="sxs-lookup"><span data-stu-id="953ae-109">Parameter and return types for the functions supported by the data store are specified in EDM terms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="953ae-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="953ae-110">Requirements</span></span>  
 <span data-ttu-id="953ae-111">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und der Datenspeicher müssen in der Lage sein, Daten in bekannten Typen ohne Datenverlust oder Abschneiden in beide Richtungen zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="953ae-111">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] and the data store need to be able to pass data back and forth in known types without any data loss or truncation.</span></span>  
  
 <span data-ttu-id="953ae-112">Das Anbietermanifest muss zur Entwurfszeit von Tools geladen werden können, ohne eine Verbindung mit dem Datenspeicher öffnen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="953ae-112">The provider manifest must be loadable by tools at design time without having to open a connection to the data store.</span></span>  
  
 <span data-ttu-id="953ae-113">Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] trifft sensibler, aber möglicherweise nicht der zugrunde liegenden Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="953ae-113">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is case sensitive, but the underlying data store may not be.</span></span> <span data-ttu-id="953ae-114">Wenn EDM-Artefakte (z. B. Bezeichner und Typnamen) im Manifest definiert und verwendet werden, muss auf die Groß- und Kleinschreibung in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] geachtet werden.</span><span class="sxs-lookup"><span data-stu-id="953ae-114">When EDM artifacts (identifiers and type names, for example) are defined and used in the manifest, they must use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] case sensitivity.</span></span> <span data-ttu-id="953ae-115">Wenn das Anbietermanifest Datenspeicherelemente enthält, bei denen die Groß-/Kleinschreibung beachtet werden muss, muss diese im Anbietermanifest beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="953ae-115">If data store elements that may be case sensitive appear in the provider manifest, that casing needs to be maintained in the provider manifest.</span></span>  
  
 <span data-ttu-id="953ae-116">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] erfordert für alle Datenanbieter ein Anbietermanifest.</span><span class="sxs-lookup"><span data-stu-id="953ae-116">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] requires a provider manifest for all data providers.</span></span> <span data-ttu-id="953ae-117">Wenn Sie versuchen, einen Anbieter zu verwenden, die nicht über kein Anbietermanifest mit der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], Sie erhalten eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="953ae-117">If you try to use a provider that does not have a provider manifest with the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], you will get an error.</span></span>  
  
 <span data-ttu-id="953ae-118">In der folgenden Tabelle werden die Arten von Ausnahmen beschrieben, die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] auslöst, wenn durch Anbieterinteraktion Ausnahmen auftreten:</span><span class="sxs-lookup"><span data-stu-id="953ae-118">The following table describes the kinds of exceptions the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] would throw when exceptions arise through provider interaction:</span></span>  
  
|<span data-ttu-id="953ae-119">Problem</span><span class="sxs-lookup"><span data-stu-id="953ae-119">Issue</span></span>|<span data-ttu-id="953ae-120">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="953ae-120">Exception</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="953ae-121">Der Anbieter unterstützt GetProviderManifest in DbProviderServices nicht.</span><span class="sxs-lookup"><span data-stu-id="953ae-121">The Provider does not support GetProviderManifest in DbProviderServices.</span></span>|<span data-ttu-id="953ae-122">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="953ae-122">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="953ae-123">Fehlendes Anbietermanifest: Beim Versuch, das Anbietermanifest abzurufen, gibt der Anbieter `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="953ae-123">Missing provider manifest: the provider returns `null` when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="953ae-124">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="953ae-124">ProviderIncompatibleException</span></span>|  
|<span data-ttu-id="953ae-125">Ungültiges Anbietermanifest: Beim Versuch, das Anbietermanifest abzurufen, gibt der Anbieter ungültiges XML zurück.</span><span class="sxs-lookup"><span data-stu-id="953ae-125">Invalid provider manifest: the provider returns invalid XML when attempting to retrieve the provider manifest.</span></span>|<span data-ttu-id="953ae-126">ProviderIncompatibleException</span><span class="sxs-lookup"><span data-stu-id="953ae-126">ProviderIncompatibleException</span></span>|  
  
## <a name="scenarios"></a><span data-ttu-id="953ae-127">Szenarien</span><span class="sxs-lookup"><span data-stu-id="953ae-127">Scenarios</span></span>  
 <span data-ttu-id="953ae-128">Ein Anbieter sollte die folgenden Szenarien unterstützen:</span><span class="sxs-lookup"><span data-stu-id="953ae-128">A provider should support the following scenarios:</span></span>  
  
### <a name="writing-a-provider-with-symmetric-type-mapping"></a><span data-ttu-id="953ae-129">Schreiben eines Anbieters mit symmetrischer Typzuordnung</span><span class="sxs-lookup"><span data-stu-id="953ae-129">Writing a Provider with Symmetric Type Mapping</span></span>  
 <span data-ttu-id="953ae-130">Sie können einen Anbieter für Schreiben der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] , in denen eine EDM-Typ, unabhängig von der zuordnungsrichtung jeder Speichertyp zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="953ae-130">You can write a provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] where each store type maps to a single EDM type, regardless of the mapping direction.</span></span> <span data-ttu-id="953ae-131">Bei Anbietertypen mit einer sehr einfachen Zuordnung, die EDM-Typen entsprechen, können Sie eine symmetrische Lösung verwenden, da das Typsystem einfach ist oder den EDM-Typen entspricht.</span><span class="sxs-lookup"><span data-stu-id="953ae-131">For a provider type that has very simple mapping that corresponds with an EDM type, you can use a symmetric solution because the type system is simple or matches EDM types.</span></span>  
  
 <span data-ttu-id="953ae-132">Sie können die Einfachheit der Domäne nutzen und ein statisches deklaratives Anbietermanifest erstellen.</span><span class="sxs-lookup"><span data-stu-id="953ae-132">You can use the simplicity of their domain and produce a static declarative provider manifest.</span></span>  
  
 <span data-ttu-id="953ae-133">Sie schreiben eine XML-Datei mit zwei Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="953ae-133">You write an XML file that has two sections:</span></span>  
  
-   <span data-ttu-id="953ae-134">Eine Liste der hinsichtlich des "EDM-Äquivalents" eines Speichertyps oder einer Funktion ausgedrückten Anbietertypen.</span><span class="sxs-lookup"><span data-stu-id="953ae-134">A list of provider types expressed in terms of the "EDM counterpart" of a store type or function.</span></span> <span data-ttu-id="953ae-135">Speichertypen verfügen über äquivalente EDM-Typen.</span><span class="sxs-lookup"><span data-stu-id="953ae-135">Store types have counterpart EDM types.</span></span> <span data-ttu-id="953ae-136">Speicherfunktionen verfügen über entsprechende EDM-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="953ae-136">Store functions have corresponding EDM functions.</span></span> <span data-ttu-id="953ae-137">So ist "varchar" z. B. ein SQL Server-Typ, der entsprechende EDM-Typ ist jedoch "string".</span><span class="sxs-lookup"><span data-stu-id="953ae-137">For example, varchar is a SQL Server type but the corresponding EDM type is string.</span></span>  
  
-   <span data-ttu-id="953ae-138">Eine Liste der vom Anbieter unterstützen Funktionen, wobei die Parameter und Rückgabetypen mit EDM-Begriffen ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="953ae-138">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
### <a name="writing-a-provider-with-asymmetric-type-mapping"></a><span data-ttu-id="953ae-139">Schreiben eines Anbieters mit asymmetrischer Typzuordnung</span><span class="sxs-lookup"><span data-stu-id="953ae-139">Writing a Provider with Asymmetric Type Mapping</span></span>  
 <span data-ttu-id="953ae-140">Wenn Sie einen Datenspeicheranbieter für [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] schreiben, unterscheidet sich die EDM-Anbieter-Typzuordnung für einige Typen möglicherweise von der Anbieter-EDM-Typzuordnung.</span><span class="sxs-lookup"><span data-stu-id="953ae-140">When writing a data store provider for the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], the EDM-to-provider type mapping for some types may be different from provider-to-EDM type mapping.</span></span> <span data-ttu-id="953ae-141">So wird beispielsweise "unbounded EDM PrimitiveTypeKind.String" möglicherweise "nvarchar (4000)" für den Anbieter zugeordnet, während "nvarchar (4000)" dem Typ "EDM PrimitiveTypeKind.String(MaxLength=4000)" zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="953ae-141">For instance, unbounded EDM PrimitiveTypeKind.String may map to nvarchar(4000) on the provider, while nvarchar(4000) maps to the EDM PrimitiveTypeKind.String(MaxLength=4000).</span></span>  
  
 <span data-ttu-id="953ae-142">Sie schreiben eine XML-Datei mit zwei Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="953ae-142">You write an XML file that has two sections:</span></span>  
  
-   <span data-ttu-id="953ae-143">Eine Liste von Anbietertypen in EDM-Begriffen sowie eine Definition der Zuordnung in beide Richtungen: EDM-Anbieter und Anbieter-EDM.</span><span class="sxs-lookup"><span data-stu-id="953ae-143">A list of provider types expressed in EDM terms and define mapping for both direction: EDM-to-provider and provider-to-EDM.</span></span>  
  
-   <span data-ttu-id="953ae-144">Eine Liste der vom Anbieter unterstützen Funktionen, wobei die Parameter und Rückgabetypen mit EDM-Begriffen ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="953ae-144">A list of functions supported by the provider where parameter and return types are expressed in EDM terms.</span></span>  
  
## <a name="provider-manifest-discoverability"></a><span data-ttu-id="953ae-145">Ermittelbarkeit des Anbietermanifests</span><span class="sxs-lookup"><span data-stu-id="953ae-145">Provider Manifest Discoverability</span></span>  
 <span data-ttu-id="953ae-146">Das Manifest wird indirekt von mehreren Komponententypen der Entitätsdienste (z. B. Tools oder Abfrage) verwendet. Die direktere Nutzung erfolgt jedoch für die Metadaten mithilfe des Metadaten-Ladeprogramms des Datenspeichers.</span><span class="sxs-lookup"><span data-stu-id="953ae-146">The manifest is used indirectly by several component types in Entity Services (for example Tools or Query) but more directly leveraged by metadata through the use of the data store metadata loader.</span></span>  
  
 <span data-ttu-id="953ae-147">![dfb3d02b&#45;7a8c&#45;4D 51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span><span class="sxs-lookup"><span data-stu-id="953ae-147">![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")</span></span>  
  
 <span data-ttu-id="953ae-148">Anbieter können jedoch unterschiedliche Speicher oder unterschiedliche Versionen des gleichen Speichers unterstützen.</span><span class="sxs-lookup"><span data-stu-id="953ae-148">However, a given provider may support different stores or different versions of the same store.</span></span> <span data-ttu-id="953ae-149">Daher muss ein Anbieter für jeden unterstützten Datenspeicher ein anderes Manifest melden.</span><span class="sxs-lookup"><span data-stu-id="953ae-149">Therefore, a provider must report a different manifest for each supported data store.</span></span>  
  
### <a name="provider-manifest-token"></a><span data-ttu-id="953ae-150">Anbietermanifesttoken</span><span class="sxs-lookup"><span data-stu-id="953ae-150">Provider Manifest Token</span></span>  
 <span data-ttu-id="953ae-151">Beim Öffnen einer Datenspeicherverbindung kann der Anbieter Informationen abfragen, um das richtige Manifest zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="953ae-151">When a data store connection is opened, the provider can query for information to return the right manifest.</span></span> <span data-ttu-id="953ae-152">Dies kann in Offlineszenarien unmöglich sein, in denen entweder die Verbindungsinformationen nicht zur Verfügung stehen oder keine Verbindung mit dem Datenspeicher hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="953ae-152">This may not be possible in offline scenarios where connection information is not available or when it is not possible to connect to the store.</span></span> <span data-ttu-id="953ae-153">Identifizieren Sie das Manifest mit dem `ProviderManifestToken`-Attribut des `Schema`-Elements in der SSDL-Datei.</span><span class="sxs-lookup"><span data-stu-id="953ae-153">Identify the manifest by using the `ProviderManifestToken` attribute of the `Schema` element in the .ssdl file.</span></span> <span data-ttu-id="953ae-154">Es gibt kein erforderliches Format für dieses Attribut. Der Anbieter wählt die Mindestinformationen aus, die erforderlich sind, um ein Manifest zu identifizieren, ohne eine Verbindung mit dem Speicher zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="953ae-154">There is no required format for this attribute; the provider chooses the minimum information needed to identify a manifest without opening a connection to the store.</span></span>  
  
 <span data-ttu-id="953ae-155">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="953ae-155">For example:</span></span>  
  
```xml  
<Schema Namespace="Northwind" Provider="System.Data.SqlClient" ProviderManifestToken="2005" xmlns:edm="http://schemas.microsoft.com/ado/2006/04/edm/ssdl" xmlns="http://schemas.microsoft.com/ado/2006/04/edm/ssdl">  
```  
  
## <a name="provider-manifest-programming-model"></a><span data-ttu-id="953ae-156">Programmiermodell für das Anbietermanifest</span><span class="sxs-lookup"><span data-stu-id="953ae-156">Provider Manifest Programming Model</span></span>  
 <span data-ttu-id="953ae-157">Anbieter werden von <xref:System.Data.Common.DbXmlEnabledProviderManifest> abgeleitet, sodass die Manifeste deklarativ angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="953ae-157">Providers derive from <xref:System.Data.Common.DbXmlEnabledProviderManifest>, which allows them to specify their manifests declaratively.</span></span> <span data-ttu-id="953ae-158">In der folgenden Abbildung wird die Klassenhierarchie eines Anbieters dargestellt:</span><span class="sxs-lookup"><span data-stu-id="953ae-158">The following illustration shows the class hierarchy of a provider:</span></span>  
  
 <span data-ttu-id="953ae-159">![Keine](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span><span class="sxs-lookup"><span data-stu-id="953ae-159">![None](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")</span></span>  
  
### <a name="discoverability-api"></a><span data-ttu-id="953ae-160">Ermittelbarkeits-API</span><span class="sxs-lookup"><span data-stu-id="953ae-160">Discoverability API</span></span>  
 <span data-ttu-id="953ae-161">Das Anbietermanifest wird vom Speichermetadaten-Ladeprogramm (StoreItemCollection) entweder über eine Datenspeicherverbindung oder mit einem Anbietermanifesttoken geladen.</span><span class="sxs-lookup"><span data-stu-id="953ae-161">The provider manifest is loaded by the Store Metadata loader (StoreItemCollection), either by using a data store connection or a provider manifest token.</span></span>  
  
#### <a name="using-a-data-store-connection"></a><span data-ttu-id="953ae-162">Verwenden einer Datenspeicherverbindung</span><span class="sxs-lookup"><span data-stu-id="953ae-162">Using a Data Store Connection</span></span>  
 <span data-ttu-id="953ae-163">Wenn die Datenspeicherverbindung verfügbar ist, rufen Sie DbProviderServices.GetProviderManifestToken auf, um das Token zurückzugeben, das an die GetProviderManifest-Methode übergeben wird, die DbProviderManifest zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="953ae-163">When the data store connection is available, call DbProvderServices.GetProviderManifestToken to return the token that is passed to the GetProviderManifest method, which returns DbProviderManifest.</span></span> <span data-ttu-id="953ae-164">Diese Methode delegiert zur Implementierung von GetDbProviderManifestToken des Anbieters.</span><span class="sxs-lookup"><span data-stu-id="953ae-164">This method delegates to the provider's implementation of GetDbProviderManifestToken.</span></span>  
  
```  
public string GetProviderManifestToken(DbConnection connection);  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
#### <a name="using-a-provider-manifest-token"></a><span data-ttu-id="953ae-165">Verwenden eines Anbietermanifesttokens</span><span class="sxs-lookup"><span data-stu-id="953ae-165">Using a Provider Manifest Token</span></span>  
 <span data-ttu-id="953ae-166">Für das Offlineszenario wird das Token der SSDL-Darstellung ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="953ae-166">For the offline scenario, the token is picked from SSDL representation.</span></span> <span data-ttu-id="953ae-167">SSDL ermöglicht das Festlegen eines ProviderManifestToken (finden Sie unter [Schema-Element (SSDL)](https://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222) Informationen).</span><span class="sxs-lookup"><span data-stu-id="953ae-167">The SSDL allows you to specify a ProviderManifestToken (see [Schema Element (SSDL)](https://msdn.microsoft.com/library/fec75ae4-7f16-4421-9265-9dac61509222) for more information).</span></span> <span data-ttu-id="953ae-168">Wenn beispielsweise eine Verbindung nicht geöffnet werden kann, verfügt SSDL über ein Anbietermanifesttoken, das Informationen über das Manifest angibt.</span><span class="sxs-lookup"><span data-stu-id="953ae-168">For example, if a connection cannot be opened, the SSDL has a provider manifest token that specifies information about the manifest.</span></span>  
  
```  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
### <a name="provider-manifest-schema"></a><span data-ttu-id="953ae-169">Anbietermanifestschema</span><span class="sxs-lookup"><span data-stu-id="953ae-169">Provider Manifest Schema</span></span>  
 <span data-ttu-id="953ae-170">Das Schema der für die einzelnen Anbieter definierten Informationen beinhaltet die statischen Informationen, die von Metadaten genutzt werden:</span><span class="sxs-lookup"><span data-stu-id="953ae-170">The schema of information defined for each provider contains the static information to be consumed by metadata:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema elementFormDefault="qualified"  
   xmlns:xs="http://www.w3.org/2001/XMLSchema"  
   targetNamespace="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest"  
   xmlns:pm="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest">  
  
  <xs:element name="ProviderManifest">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Types" type="pm:TTypes" minOccurs="1" maxOccurs="1" />  
        <xs:element name="Functions" type="pm:TFunctions" minOccurs="0" maxOccurs="1"/>  
      </xs:sequence>  
      <xs:attribute name="Namespace" type="xs:string" use="required"/>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="TVersion">  
    <xs:attribute name="Major" type="xs:int" use="required" />  
    <xs:attribute name="Minor" type="xs:int" use="required" />  
    <xs:attribute name="Build" type="xs:int" use="required" />  
    <xs:attribute name="Revision" type="xs:int" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TIntegerFacetDescription">  
    <xs:attribute name="Minimum" type="xs:int" use="optional" />  
    <xs:attribute name="Maximum" type="xs:int" use="optional" />  
    <xs:attribute name="DefaultValue" type="xs:int" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TBooleanFacetDescription">  
    <xs:attribute name="DefaultValue" type="xs:boolean" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="true" />  
  </xs:complexType>  
  
  <xs:complexType name="TDateTimeFacetDescription">  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TFacetDescriptions">  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="Precision" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Scale" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="MaxLength" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Unicode" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
      <xs:element name="FixedLength" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:complexType name="TType">  
    <xs:sequence>  
      <xs:element name="FacetDescriptions" type="pm:TFacetDescriptions" minOccurs="0" maxOccurs="1"/>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required"/>  
    <xs:attribute name="PrimitiveTypeKind" type="pm:TPrimitiveTypeKind" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TTypes">  
    <xs:sequence>  
      <xs:element name="Type" type="pm:TType" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:attributeGroup name="TFacetAttribute">  
    <xs:attribute name="Precision" type="xs:int" use="optional"/>  
    <xs:attribute name="Scale" type="xs:int" use="optional"/>  
    <xs:attribute name="MaxLength" type="xs:int" use="optional"/>  
    <xs:attribute name="Unicode" type="xs:boolean" use="optional"/>  
    <xs:attribute name="FixedLength" type="xs:boolean" use="optional"/>  
  </xs:attributeGroup>  
  
  <xs:complexType name="TFunctionParameter">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
    <xs:attribute name="Mode" type="pm:TParameterDirection" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TReturnType">  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunction">  
    <xs:choice minOccurs="0" maxOccurs ="unbounded">  
      <xs:element name ="ReturnType" type="pm:TReturnType" minOccurs="0" maxOccurs="1" />  
      <xs:element name="Parameter" type="pm:TFunctionParameter" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:choice>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Aggregate" type="xs:boolean" use="optional" />  
    <xs:attribute name="BuiltIn" type="xs:boolean" use="optional" />  
    <xs:attribute name="StoreFunctionName" type="xs:string" use="optional" />  
    <xs:attribute name="NiladicFunction" type="xs:boolean" use="optional" />  
    <xs:attribute name="ParameterTypeSemantics" type="pm:TParameterTypeSemantics" use="optional" default="AllowImplicitConversion" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunctions">  
    <xs:sequence>  
      <xs:element name="Function" type="pm:TFunction" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:simpleType name="TPrimitiveTypeKind">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Binary"/>  
      <xs:enumeration value="Boolean"/>  
      <xs:enumeration value="Byte"/>  
      <xs:enumeration value="Decimal"/>  
      <xs:enumeration value="DateTime"/>  
      <xs:enumeration value="Time"/>  
      <xs:enumeration value="DateTimeOffset"/>          
      <xs:enumeration value="Double"/>  
      <xs:enumeration value="Guid"/>  
      <xs:enumeration value="Single"/>  
      <xs:enumeration value="SByte"/>  
      <xs:enumeration value="Int16"/>  
      <xs:enumeration value="Int32"/>  
      <xs:enumeration value="Int64"/>  
      <xs:enumeration value="String"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In"/>  
      <xs:enumeration value="Out"/>  
      <xs:enumeration value="InOut"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterTypeSemantics">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="ExactMatchOnly" />  
      <xs:enumeration value="AllowImplicitPromotion" />  
      <xs:enumeration value="AllowImplicitConversion" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
#### <a name="types-node"></a><span data-ttu-id="953ae-171">Typknoten</span><span class="sxs-lookup"><span data-stu-id="953ae-171">Types Node</span></span>  
 <span data-ttu-id="953ae-172">Der Typknoten des Anbietermanifests enthält Informationen über die Typen, die vom Datenspeicher oder Anbieter systemeigen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="953ae-172">The Types node in the provider manifest contains information about the Types that are supported natively by the data store or through the provider.</span></span>  
  
##### <a name="type-node"></a><span data-ttu-id="953ae-173">Typknoten</span><span class="sxs-lookup"><span data-stu-id="953ae-173">Type Node</span></span>  
 <span data-ttu-id="953ae-174">Jeder Typknoten definiert einen Anbietertyp mit EDM-Begriffen.</span><span class="sxs-lookup"><span data-stu-id="953ae-174">Each Type node defines a provider type in terms of EDM.</span></span> <span data-ttu-id="953ae-175">Der Typknoten beschreibt den Namen des Anbietertyps, Informationen über den Modelltyp, dem er zugeordnet wird, und die Facets, mit denen die Typzuordnung beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="953ae-175">The Type node describes the name of the provider type, and information related to the model type it maps to and facets to describe that type mapping.</span></span>  
  
 <span data-ttu-id="953ae-176">Um diese Typinformationen im Anbietermanifest auszudrücken, muss jede TypeInformation-Deklaration mehrere Facetbeschreibungen für die einzelnen Typen definieren:</span><span class="sxs-lookup"><span data-stu-id="953ae-176">In order to express this type information in the provider manifest, each TypeInformation declaration must define several facet descriptions for each Type:</span></span>  
  
|<span data-ttu-id="953ae-177">Attributname</span><span class="sxs-lookup"><span data-stu-id="953ae-177">Attribute Name</span></span>|<span data-ttu-id="953ae-178">Datentyp</span><span class="sxs-lookup"><span data-stu-id="953ae-178">Data Type</span></span>|<span data-ttu-id="953ae-179">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="953ae-179">Required</span></span>|<span data-ttu-id="953ae-180">Standardwert</span><span class="sxs-lookup"><span data-stu-id="953ae-180">Default Value</span></span>|<span data-ttu-id="953ae-181">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="953ae-181">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="953ae-182">Name</span><span class="sxs-lookup"><span data-stu-id="953ae-182">Name</span></span>|<span data-ttu-id="953ae-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="953ae-183">String</span></span>|<span data-ttu-id="953ae-184">Ja</span><span class="sxs-lookup"><span data-stu-id="953ae-184">Yes</span></span>|<span data-ttu-id="953ae-185">nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="953ae-185">n/a</span></span>|<span data-ttu-id="953ae-186">Anbieterspezifischer Datentypname</span><span class="sxs-lookup"><span data-stu-id="953ae-186">Provider-specific data type name</span></span>|  
|<span data-ttu-id="953ae-187">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="953ae-187">PrimitiveTypeKind</span></span>|<span data-ttu-id="953ae-188">PrimitiveTypeKind</span><span class="sxs-lookup"><span data-stu-id="953ae-188">PrimitiveTypeKind</span></span>|<span data-ttu-id="953ae-189">Ja</span><span class="sxs-lookup"><span data-stu-id="953ae-189">Yes</span></span>|<span data-ttu-id="953ae-190">nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="953ae-190">n/a</span></span>|<span data-ttu-id="953ae-191">EDM-Typenname</span><span class="sxs-lookup"><span data-stu-id="953ae-191">EDM type name</span></span>|  
  
###### <a name="function-node"></a><span data-ttu-id="953ae-192">Funktionsknoten</span><span class="sxs-lookup"><span data-stu-id="953ae-192">Function Node</span></span>  
 <span data-ttu-id="953ae-193">Jede Funktion definiert eine einzelne, über den Anbieter verfügbare Funktion.</span><span class="sxs-lookup"><span data-stu-id="953ae-193">Each Function defines a single function available through the provider.</span></span>  
  
|<span data-ttu-id="953ae-194">Attributname</span><span class="sxs-lookup"><span data-stu-id="953ae-194">Attribute Name</span></span>|<span data-ttu-id="953ae-195">Datentyp</span><span class="sxs-lookup"><span data-stu-id="953ae-195">Data Type</span></span>|<span data-ttu-id="953ae-196">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="953ae-196">Required</span></span>|<span data-ttu-id="953ae-197">Standardwert</span><span class="sxs-lookup"><span data-stu-id="953ae-197">Default Value</span></span>|<span data-ttu-id="953ae-198">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="953ae-198">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="953ae-199">Name</span><span class="sxs-lookup"><span data-stu-id="953ae-199">Name</span></span>|<span data-ttu-id="953ae-200">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="953ae-200">String</span></span>|<span data-ttu-id="953ae-201">Ja</span><span class="sxs-lookup"><span data-stu-id="953ae-201">Yes</span></span>|<span data-ttu-id="953ae-202">nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="953ae-202">n/a</span></span>|<span data-ttu-id="953ae-203">Bezeichner/Name der Funktion</span><span class="sxs-lookup"><span data-stu-id="953ae-203">Identifier/name of the function</span></span>|  
|<span data-ttu-id="953ae-204">ReturnType</span><span class="sxs-lookup"><span data-stu-id="953ae-204">ReturnType</span></span>|<span data-ttu-id="953ae-205">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="953ae-205">String</span></span>|<span data-ttu-id="953ae-206">Nein</span><span class="sxs-lookup"><span data-stu-id="953ae-206">No</span></span>|<span data-ttu-id="953ae-207">Void</span><span class="sxs-lookup"><span data-stu-id="953ae-207">Void</span></span>|<span data-ttu-id="953ae-208">Der EDM-Rückgabetyp der Funktion</span><span class="sxs-lookup"><span data-stu-id="953ae-208">The EDM return type of the function</span></span>|  
|<span data-ttu-id="953ae-209">Aggregat</span><span class="sxs-lookup"><span data-stu-id="953ae-209">Aggregate</span></span>|<span data-ttu-id="953ae-210">Boolean</span><span class="sxs-lookup"><span data-stu-id="953ae-210">Boolean</span></span>|<span data-ttu-id="953ae-211">Nein</span><span class="sxs-lookup"><span data-stu-id="953ae-211">No</span></span>|<span data-ttu-id="953ae-212">False</span><span class="sxs-lookup"><span data-stu-id="953ae-212">False</span></span>|<span data-ttu-id="953ae-213">"True", wenn es sich bei der Funktion um eine Aggregatfunktion handelt.</span><span class="sxs-lookup"><span data-stu-id="953ae-213">True if the function is an aggregate function</span></span>|  
|<span data-ttu-id="953ae-214">BuiltIn</span><span class="sxs-lookup"><span data-stu-id="953ae-214">BuiltIn</span></span>|<span data-ttu-id="953ae-215">Boolean</span><span class="sxs-lookup"><span data-stu-id="953ae-215">Boolean</span></span>|<span data-ttu-id="953ae-216">Nein</span><span class="sxs-lookup"><span data-stu-id="953ae-216">No</span></span>|<span data-ttu-id="953ae-217">True</span><span class="sxs-lookup"><span data-stu-id="953ae-217">True</span></span>|<span data-ttu-id="953ae-218">"True", wenn die Funktion in den Datenspeicher integriert ist.</span><span class="sxs-lookup"><span data-stu-id="953ae-218">True if the function is built into the data store</span></span>|  
|<span data-ttu-id="953ae-219">StoreFunctionName</span><span class="sxs-lookup"><span data-stu-id="953ae-219">StoreFunctionName</span></span>|<span data-ttu-id="953ae-220">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="953ae-220">String</span></span>|<span data-ttu-id="953ae-221">Nein</span><span class="sxs-lookup"><span data-stu-id="953ae-221">No</span></span>|<span data-ttu-id="953ae-222">\<Name ></span><span class="sxs-lookup"><span data-stu-id="953ae-222">\<Name></span></span>|<span data-ttu-id="953ae-223">Funktionsname im Datenspeicher.</span><span class="sxs-lookup"><span data-stu-id="953ae-223">Function Name in the data store.</span></span>  <span data-ttu-id="953ae-224">Ermöglicht eine Umleitungsebene für Funktionsnamen.</span><span class="sxs-lookup"><span data-stu-id="953ae-224">Allows for a level of redirection of function names.</span></span>|  
|<span data-ttu-id="953ae-225">NiladicFunction</span><span class="sxs-lookup"><span data-stu-id="953ae-225">NiladicFunction</span></span>|<span data-ttu-id="953ae-226">Boolean</span><span class="sxs-lookup"><span data-stu-id="953ae-226">Boolean</span></span>|<span data-ttu-id="953ae-227">Nein</span><span class="sxs-lookup"><span data-stu-id="953ae-227">No</span></span>|<span data-ttu-id="953ae-228">False</span><span class="sxs-lookup"><span data-stu-id="953ae-228">False</span></span>|<span data-ttu-id="953ae-229">"True", wenn die Funktion keine Parameter erfordert und ohne Parameter aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="953ae-229">True if the function does not require parameters and is called without any parameters</span></span>|  
|<span data-ttu-id="953ae-230">ParameterType</span><span class="sxs-lookup"><span data-stu-id="953ae-230">ParameterType</span></span><br /><br /> <span data-ttu-id="953ae-231">Semantik</span><span class="sxs-lookup"><span data-stu-id="953ae-231">Semantics</span></span>|<span data-ttu-id="953ae-232">ParameterSemantics</span><span class="sxs-lookup"><span data-stu-id="953ae-232">ParameterSemantics</span></span>|<span data-ttu-id="953ae-233">Nein</span><span class="sxs-lookup"><span data-stu-id="953ae-233">No</span></span>|<span data-ttu-id="953ae-234">AllowImplicit</span><span class="sxs-lookup"><span data-stu-id="953ae-234">AllowImplicit</span></span><br /><br /> <span data-ttu-id="953ae-235">Conversion</span><span class="sxs-lookup"><span data-stu-id="953ae-235">Conversion</span></span>|<span data-ttu-id="953ae-236">Hiermit kann ausgewählt werden, wie die Abfragepipeline mit Parametertypersetzung umgehen soll:</span><span class="sxs-lookup"><span data-stu-id="953ae-236">Choice of how the query pipeline should deal with parameter type substitution:</span></span><br /><br /> <span data-ttu-id="953ae-237">-ExactMatchOnly</span><span class="sxs-lookup"><span data-stu-id="953ae-237">-   ExactMatchOnly</span></span><br /><span data-ttu-id="953ae-238">-AllowImplicitPromotion</span><span class="sxs-lookup"><span data-stu-id="953ae-238">-   AllowImplicitPromotion</span></span><br /><span data-ttu-id="953ae-239">-AllowImplicitConversion</span><span class="sxs-lookup"><span data-stu-id="953ae-239">-   AllowImplicitConversion</span></span>|  
  
 <span data-ttu-id="953ae-240">**Parameterknoten**</span><span class="sxs-lookup"><span data-stu-id="953ae-240">**Parameters Node**</span></span>  
  
 <span data-ttu-id="953ae-241">Jede Funktion verfügt über eine Auflistung von einem oder mehreren Parameterknoten.</span><span class="sxs-lookup"><span data-stu-id="953ae-241">Each function has a collection of one or more Parameter nodes.</span></span>  
  
|<span data-ttu-id="953ae-242">Attributname</span><span class="sxs-lookup"><span data-stu-id="953ae-242">Attribute Name</span></span>|<span data-ttu-id="953ae-243">Datentyp</span><span class="sxs-lookup"><span data-stu-id="953ae-243">Data Type</span></span>|<span data-ttu-id="953ae-244">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="953ae-244">Required</span></span>|<span data-ttu-id="953ae-245">Standardwert</span><span class="sxs-lookup"><span data-stu-id="953ae-245">Default Value</span></span>|<span data-ttu-id="953ae-246">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="953ae-246">Description</span></span>|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|<span data-ttu-id="953ae-247">Name</span><span class="sxs-lookup"><span data-stu-id="953ae-247">Name</span></span>|<span data-ttu-id="953ae-248">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="953ae-248">String</span></span>|<span data-ttu-id="953ae-249">Ja</span><span class="sxs-lookup"><span data-stu-id="953ae-249">Yes</span></span>|<span data-ttu-id="953ae-250">nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="953ae-250">n/a</span></span>|<span data-ttu-id="953ae-251">Bezeichner/Name des Parameters.</span><span class="sxs-lookup"><span data-stu-id="953ae-251">Identifier/name of the parameter.</span></span>|  
|<span data-ttu-id="953ae-252">Typ</span><span class="sxs-lookup"><span data-stu-id="953ae-252">Type</span></span>|<span data-ttu-id="953ae-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="953ae-253">String</span></span>|<span data-ttu-id="953ae-254">Ja</span><span class="sxs-lookup"><span data-stu-id="953ae-254">Yes</span></span>|<span data-ttu-id="953ae-255">nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="953ae-255">n/a</span></span>|<span data-ttu-id="953ae-256">Der EDM-Typ des Parameters.</span><span class="sxs-lookup"><span data-stu-id="953ae-256">The EDM type of the parameter.</span></span>|  
|<span data-ttu-id="953ae-257">Modus</span><span class="sxs-lookup"><span data-stu-id="953ae-257">Mode</span></span>|<span data-ttu-id="953ae-258">Parameter</span><span class="sxs-lookup"><span data-stu-id="953ae-258">Parameter</span></span><br /><br /> <span data-ttu-id="953ae-259">Richtung</span><span class="sxs-lookup"><span data-stu-id="953ae-259">Direction</span></span>|<span data-ttu-id="953ae-260">Ja</span><span class="sxs-lookup"><span data-stu-id="953ae-260">Yes</span></span>|<span data-ttu-id="953ae-261">nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="953ae-261">n/a</span></span>|<span data-ttu-id="953ae-262">Richtung des Parameters:</span><span class="sxs-lookup"><span data-stu-id="953ae-262">Direction of parameter:</span></span><br /><br /> <span data-ttu-id="953ae-263">-in</span><span class="sxs-lookup"><span data-stu-id="953ae-263">-   in</span></span><br /><span data-ttu-id="953ae-264">-out</span><span class="sxs-lookup"><span data-stu-id="953ae-264">-   out</span></span><br /><span data-ttu-id="953ae-265">-inout</span><span class="sxs-lookup"><span data-stu-id="953ae-265">-   inout</span></span>|  
  
##### <a name="namespace-attribute"></a><span data-ttu-id="953ae-266">Namespace-Attribut</span><span class="sxs-lookup"><span data-stu-id="953ae-266">Namespace Attribute</span></span>  
 <span data-ttu-id="953ae-267">Jeder Datenspeicheranbieter muss einen Namespace oder eine Gruppe von Namespaces für die im Manifest definierten Informationen definieren.</span><span class="sxs-lookup"><span data-stu-id="953ae-267">Each data store provider must define a namespace or group of namespaces for information defined in the manifest.</span></span> <span data-ttu-id="953ae-268">Dieser Namespace kann in Entity SQL-Abfragen verwendet werden, um Namen von Funktionen und Typen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="953ae-268">This namespace can be used in Entity SQL queries to resolve names of functions and types.</span></span> <span data-ttu-id="953ae-269">Zum Beispiel: SqlServer.</span><span class="sxs-lookup"><span data-stu-id="953ae-269">For instance: SqlServer.</span></span> <span data-ttu-id="953ae-270">Dieser Namespace muss sich vom kanonischen Namespace "EDM" unterscheiden, der von den Entitätsdiensten für Standardfunktionen definiert wird, die von Entity SQL-Abfragen unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="953ae-270">That namespace must be different from the canonical namespace, EDM, defined by Entity Services for standard functions to be supported by Entity SQL queries.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="953ae-271">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="953ae-271">See Also</span></span>  
 [<span data-ttu-id="953ae-272">Schreiben eines Entity Framework-Datenanbieters</span><span class="sxs-lookup"><span data-stu-id="953ae-272">Writing an Entity Framework Data Provider</span></span>](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
