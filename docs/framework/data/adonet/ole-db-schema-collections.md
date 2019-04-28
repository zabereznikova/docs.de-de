---
title: OLE DB-Schemaauflistungen
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771994"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="7ac87-102">OLE DB-Schemaauflistungen</span><span class="sxs-lookup"><span data-stu-id="7ac87-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="7ac87-103">In diesem Abschnitt wird die Unterstützung von Schemaauflistungen für die ODBC-Anbieter für Microsoft SQL Server, Oracle und Microsoft Jet diskutiert.</span><span class="sxs-lookup"><span data-stu-id="7ac87-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="7ac87-104">Microsoft SQL Server-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="7ac87-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="7ac87-105">Der Microsoft SQL Server OLE DB-Treiber unterstützt neben den allgemeinen schemaauflistungen die folgenden spezifischen schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="7ac87-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="7ac87-106">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7ac87-106">Tables</span></span>  
  
- <span data-ttu-id="7ac87-107">Spalten</span><span class="sxs-lookup"><span data-stu-id="7ac87-107">Columns</span></span>  
  
- <span data-ttu-id="7ac87-108">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7ac87-108">Procedures</span></span>  
  
- <span data-ttu-id="7ac87-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7ac87-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="7ac87-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="7ac87-110">Catalog</span></span>  
  
- <span data-ttu-id="7ac87-111">Indizes</span><span class="sxs-lookup"><span data-stu-id="7ac87-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7ac87-112">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7ac87-112">Tables</span></span>  
  
|<span data-ttu-id="7ac87-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-113">ColumnName</span></span>|<span data-ttu-id="7ac87-114">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-115">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-116">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-116">String</span></span>|  
|<span data-ttu-id="7ac87-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-118">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-118">String</span></span>|  
|<span data-ttu-id="7ac87-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-119">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-120">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-120">String</span></span>|  
|<span data-ttu-id="7ac87-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-121">TABLE_TYPE</span></span>|<span data-ttu-id="7ac87-122">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-122">String</span></span>|  
|<span data-ttu-id="7ac87-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-123">TABLE_GUID</span></span>|<span data-ttu-id="7ac87-124">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-124">Guid</span></span>|  
|<span data-ttu-id="7ac87-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-125">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-126">String</span></span>|  
|<span data-ttu-id="7ac87-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-127">TABLE_PROPID</span></span>|<span data-ttu-id="7ac87-128">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-128">Int64</span></span>|  
|<span data-ttu-id="7ac87-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-129">DATE_CREATED</span></span>|<span data-ttu-id="7ac87-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-130">DateTime</span></span>|  
|<span data-ttu-id="7ac87-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7ac87-131">DATE_MODIFIED</span></span>|<span data-ttu-id="7ac87-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7ac87-133">Spalten</span><span class="sxs-lookup"><span data-stu-id="7ac87-133">Columns</span></span>  
  
|<span data-ttu-id="7ac87-134">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-134">ColumnName</span></span>|<span data-ttu-id="7ac87-135">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-136">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-137">String</span></span>|  
|<span data-ttu-id="7ac87-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-139">String</span></span>|  
|<span data-ttu-id="7ac87-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-140">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-141">String</span></span>|  
|<span data-ttu-id="7ac87-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-142">COLUMN_NAME</span></span>|<span data-ttu-id="7ac87-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-143">String</span></span>|  
|<span data-ttu-id="7ac87-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-144">COLUMN_GUID</span></span>|<span data-ttu-id="7ac87-145">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-145">Guid</span></span>|  
|<span data-ttu-id="7ac87-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-146">COLUMN_PROPID</span></span>|<span data-ttu-id="7ac87-147">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-147">Int64</span></span>|  
|<span data-ttu-id="7ac87-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="7ac87-149">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-149">Int64</span></span>|  
|<span data-ttu-id="7ac87-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7ac87-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7ac87-151">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-151">Boolean</span></span>|  
|<span data-ttu-id="7ac87-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7ac87-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7ac87-153">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-153">String</span></span>|  
|<span data-ttu-id="7ac87-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7ac87-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="7ac87-155">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-155">Int64</span></span>|  
|<span data-ttu-id="7ac87-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7ac87-156">IS_NULLABLE</span></span>|<span data-ttu-id="7ac87-157">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-157">Boolean</span></span>|  
|<span data-ttu-id="7ac87-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-158">DATA_TYPE</span></span>|<span data-ttu-id="7ac87-159">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-159">Int32</span></span>|  
|<span data-ttu-id="7ac87-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-160">TYPE_GUID</span></span>|<span data-ttu-id="7ac87-161">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-161">Guid</span></span>|  
|<span data-ttu-id="7ac87-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7ac87-163">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-163">Int64</span></span>|  
|<span data-ttu-id="7ac87-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7ac87-165">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-165">Int64</span></span>|  
|<span data-ttu-id="7ac87-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7ac87-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7ac87-167">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-167">Int32</span></span>|  
|<span data-ttu-id="7ac87-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7ac87-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="7ac87-169">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-169">Int16</span></span>|  
|<span data-ttu-id="7ac87-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7ac87-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="7ac87-171">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-171">Int64</span></span>|  
|<span data-ttu-id="7ac87-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7ac87-173">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-173">String</span></span>|  
|<span data-ttu-id="7ac87-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7ac87-175">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-175">String</span></span>|  
|<span data-ttu-id="7ac87-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7ac87-177">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-177">String</span></span>|  
|<span data-ttu-id="7ac87-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="7ac87-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-179">String</span></span>|  
|<span data-ttu-id="7ac87-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7ac87-181">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-181">String</span></span>|  
|<span data-ttu-id="7ac87-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-182">COLLATION_NAME</span></span>|<span data-ttu-id="7ac87-183">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-183">String</span></span>|  
|<span data-ttu-id="7ac87-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7ac87-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-185">String</span></span>|  
|<span data-ttu-id="7ac87-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7ac87-187">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-187">String</span></span>|  
|<span data-ttu-id="7ac87-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-188">DOMAIN_NAME</span></span>|<span data-ttu-id="7ac87-189">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-189">String</span></span>|  
|<span data-ttu-id="7ac87-190">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-190">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-191">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-191">String</span></span>|  
|<span data-ttu-id="7ac87-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="7ac87-192">COLUMN_LCID</span></span>|<span data-ttu-id="7ac87-193">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-193">Int32</span></span>|  
|<span data-ttu-id="7ac87-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="7ac87-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="7ac87-195">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-195">Int32</span></span>|  
|<span data-ttu-id="7ac87-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="7ac87-196">COLUMN_SORTID</span></span>|<span data-ttu-id="7ac87-197">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-197">Int32</span></span>|  
|<span data-ttu-id="7ac87-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="7ac87-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="7ac87-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="7ac87-199">Byte[]</span></span>|  
|<span data-ttu-id="7ac87-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="7ac87-200">IS_COMPUTED</span></span>|<span data-ttu-id="7ac87-201">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7ac87-202">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7ac87-202">Procedures</span></span>  
  
|<span data-ttu-id="7ac87-203">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-203">ColumnName</span></span>|<span data-ttu-id="7ac87-204">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7ac87-206">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-206">String</span></span>|  
|<span data-ttu-id="7ac87-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7ac87-208">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-208">String</span></span>|  
|<span data-ttu-id="7ac87-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="7ac87-210">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-210">String</span></span>|  
|<span data-ttu-id="7ac87-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7ac87-212">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-212">Int16</span></span>|  
|<span data-ttu-id="7ac87-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7ac87-214">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-214">String</span></span>|  
|<span data-ttu-id="7ac87-215">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-215">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-216">String</span></span>|  
|<span data-ttu-id="7ac87-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-217">DATE_CREATED</span></span>|<span data-ttu-id="7ac87-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-218">DateTime</span></span>|  
|<span data-ttu-id="7ac87-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7ac87-219">DATE_MODIFIED</span></span>|<span data-ttu-id="7ac87-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="7ac87-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7ac87-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="7ac87-222">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-222">ColumnName</span></span>|<span data-ttu-id="7ac87-223">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7ac87-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-225">String</span></span>|  
|<span data-ttu-id="7ac87-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7ac87-227">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-227">String</span></span>|  
|<span data-ttu-id="7ac87-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="7ac87-229">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-229">String</span></span>|  
|<span data-ttu-id="7ac87-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-230">PARAMETER_NAME</span></span>|<span data-ttu-id="7ac87-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-231">String</span></span>|  
|<span data-ttu-id="7ac87-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="7ac87-233">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-233">Int32</span></span>|  
|<span data-ttu-id="7ac87-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="7ac87-235">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-235">Int32</span></span>|  
|<span data-ttu-id="7ac87-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7ac87-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="7ac87-237">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-237">Boolean</span></span>|  
|<span data-ttu-id="7ac87-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7ac87-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="7ac87-239">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-239">String</span></span>|  
|<span data-ttu-id="7ac87-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7ac87-240">IS_NULLABLE</span></span>|<span data-ttu-id="7ac87-241">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-241">Boolean</span></span>|  
|<span data-ttu-id="7ac87-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-242">DATA_TYPE</span></span>|<span data-ttu-id="7ac87-243">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-243">Int32</span></span>|  
|<span data-ttu-id="7ac87-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7ac87-245">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-245">Int64</span></span>|  
|<span data-ttu-id="7ac87-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7ac87-247">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-247">Int64</span></span>|  
|<span data-ttu-id="7ac87-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7ac87-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7ac87-249">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-249">Int32</span></span>|  
|<span data-ttu-id="7ac87-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7ac87-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="7ac87-251">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-251">Int16</span></span>|  
|<span data-ttu-id="7ac87-252">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-252">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-253">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-253">String</span></span>|  
|<span data-ttu-id="7ac87-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-254">TYPE_NAME</span></span>|<span data-ttu-id="7ac87-255">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-255">String</span></span>|  
|<span data-ttu-id="7ac87-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="7ac87-257">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="7ac87-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="7ac87-258">Catalog</span></span>  
  
|<span data-ttu-id="7ac87-259">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-259">ColumnName</span></span>|<span data-ttu-id="7ac87-260">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-261">CATALOG_NAME</span></span>|<span data-ttu-id="7ac87-262">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-262">String</span></span>|  
|<span data-ttu-id="7ac87-263">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-263">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-264">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7ac87-265">Indizes</span><span class="sxs-lookup"><span data-stu-id="7ac87-265">Indexes</span></span>  
  
|<span data-ttu-id="7ac87-266">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-266">ColumnName</span></span>|<span data-ttu-id="7ac87-267">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-268">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-269">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-269">String</span></span>|  
|<span data-ttu-id="7ac87-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-271">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-271">String</span></span>|  
|<span data-ttu-id="7ac87-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-272">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-273">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-273">String</span></span>|  
|<span data-ttu-id="7ac87-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-274">INDEX_CATALOG</span></span>|<span data-ttu-id="7ac87-275">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-275">String</span></span>|  
|<span data-ttu-id="7ac87-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="7ac87-277">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-277">String</span></span>|  
|<span data-ttu-id="7ac87-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-278">INDEX_NAME</span></span>|<span data-ttu-id="7ac87-279">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-279">String</span></span>|  
|<span data-ttu-id="7ac87-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7ac87-280">PRIMARY_KEY</span></span>|<span data-ttu-id="7ac87-281">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-281">Boolean</span></span>|  
|<span data-ttu-id="7ac87-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7ac87-282">UNIQUE</span></span>|<span data-ttu-id="7ac87-283">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-283">Boolean</span></span>|  
|<span data-ttu-id="7ac87-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7ac87-284">CLUSTERED</span></span>|<span data-ttu-id="7ac87-285">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-285">Boolean</span></span>|  
|<span data-ttu-id="7ac87-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-286">TYPE</span></span>|<span data-ttu-id="7ac87-287">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-287">Int32</span></span>|  
|<span data-ttu-id="7ac87-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7ac87-288">FILL_FACTOR</span></span>|<span data-ttu-id="7ac87-289">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-289">Int32</span></span>|  
|<span data-ttu-id="7ac87-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7ac87-290">INITIAL_SIZE</span></span>|<span data-ttu-id="7ac87-291">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-291">Int32</span></span>|  
|<span data-ttu-id="7ac87-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="7ac87-292">NULLS</span></span>|<span data-ttu-id="7ac87-293">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-293">Int32</span></span>|  
|<span data-ttu-id="7ac87-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7ac87-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7ac87-295">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-295">Boolean</span></span>|  
|<span data-ttu-id="7ac87-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7ac87-296">AUTO_UPDATE</span></span>|<span data-ttu-id="7ac87-297">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-297">Boolean</span></span>|  
|<span data-ttu-id="7ac87-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7ac87-298">NULL_COLLATION</span></span>|<span data-ttu-id="7ac87-299">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-299">Int32</span></span>|  
|<span data-ttu-id="7ac87-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="7ac87-301">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-301">Int64</span></span>|  
|<span data-ttu-id="7ac87-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-302">COLUMN_NAME</span></span>|<span data-ttu-id="7ac87-303">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-303">String</span></span>|  
|<span data-ttu-id="7ac87-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-304">COLUMN_GUID</span></span>|<span data-ttu-id="7ac87-305">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-305">Guid</span></span>|  
|<span data-ttu-id="7ac87-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-306">COLUMN_PROPID</span></span>|<span data-ttu-id="7ac87-307">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-307">Int64</span></span>|  
|<span data-ttu-id="7ac87-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7ac87-308">COLLATION</span></span>|<span data-ttu-id="7ac87-309">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-309">Int16</span></span>|  
|<span data-ttu-id="7ac87-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7ac87-310">CARDINALITY</span></span>|<span data-ttu-id="7ac87-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="7ac87-311">Decimal</span></span>|  
|<span data-ttu-id="7ac87-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="7ac87-312">PAGES</span></span>|<span data-ttu-id="7ac87-313">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-313">Int32</span></span>|  
|<span data-ttu-id="7ac87-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-314">FILTER_CONDITION</span></span>|<span data-ttu-id="7ac87-315">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-315">String</span></span>|  
|<span data-ttu-id="7ac87-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-316">INTEGRATED</span></span>|<span data-ttu-id="7ac87-317">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="7ac87-318">Microsoft Oracle-OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="7ac87-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="7ac87-319">Der Microsoft Oracle OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="7ac87-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="7ac87-320">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7ac87-320">Tables</span></span>  
  
- <span data-ttu-id="7ac87-321">Spalten</span><span class="sxs-lookup"><span data-stu-id="7ac87-321">Columns</span></span>  
  
- <span data-ttu-id="7ac87-322">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7ac87-322">Procedures</span></span>  
  
- <span data-ttu-id="7ac87-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7ac87-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="7ac87-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="7ac87-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="7ac87-325">Ansichten</span><span class="sxs-lookup"><span data-stu-id="7ac87-325">Views</span></span>  
  
- <span data-ttu-id="7ac87-326">Indizes</span><span class="sxs-lookup"><span data-stu-id="7ac87-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7ac87-327">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7ac87-327">Tables</span></span>  
  
|<span data-ttu-id="7ac87-328">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-328">ColumnName</span></span>|<span data-ttu-id="7ac87-329">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-330">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-331">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-331">String</span></span>|  
|<span data-ttu-id="7ac87-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-333">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-333">String</span></span>|  
|<span data-ttu-id="7ac87-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-334">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-335">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-335">String</span></span>|  
|<span data-ttu-id="7ac87-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-336">TABLE_TYPE</span></span>|<span data-ttu-id="7ac87-337">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-337">String</span></span>|  
|<span data-ttu-id="7ac87-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-338">TABLE_GUID</span></span>|<span data-ttu-id="7ac87-339">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-339">Guid</span></span>|  
|<span data-ttu-id="7ac87-340">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-340">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-341">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-341">String</span></span>|  
|<span data-ttu-id="7ac87-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-342">TABLE_PROPID</span></span>|<span data-ttu-id="7ac87-343">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-343">Int64</span></span>|  
|<span data-ttu-id="7ac87-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-344">DATE_CREATED</span></span>|<span data-ttu-id="7ac87-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-345">DateTime</span></span>|  
|<span data-ttu-id="7ac87-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7ac87-346">DATE_MODIFIED</span></span>|<span data-ttu-id="7ac87-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7ac87-348">Spalten</span><span class="sxs-lookup"><span data-stu-id="7ac87-348">Columns</span></span>  
  
|<span data-ttu-id="7ac87-349">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-349">ColumnName</span></span>|<span data-ttu-id="7ac87-350">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-351">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-352">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-352">String</span></span>|  
|<span data-ttu-id="7ac87-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-354">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-354">String</span></span>|  
|<span data-ttu-id="7ac87-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-355">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-356">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-356">String</span></span>|  
|<span data-ttu-id="7ac87-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-357">COLUMN_NAME</span></span>|<span data-ttu-id="7ac87-358">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-358">String</span></span>|  
|<span data-ttu-id="7ac87-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-359">COLUMN_GUID</span></span>|<span data-ttu-id="7ac87-360">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-360">Guid</span></span>|  
|<span data-ttu-id="7ac87-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-361">COLUMN_PROPID</span></span>|<span data-ttu-id="7ac87-362">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-362">Int64</span></span>|  
|<span data-ttu-id="7ac87-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="7ac87-364">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-364">Int64</span></span>|  
|<span data-ttu-id="7ac87-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7ac87-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7ac87-366">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-366">Boolean</span></span>|  
|<span data-ttu-id="7ac87-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7ac87-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7ac87-368">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-368">String</span></span>|  
|<span data-ttu-id="7ac87-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7ac87-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="7ac87-370">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-370">Int64</span></span>|  
|<span data-ttu-id="7ac87-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7ac87-371">IS_NULLABLE</span></span>|<span data-ttu-id="7ac87-372">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-372">Boolean</span></span>|  
|<span data-ttu-id="7ac87-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-373">DATA_TYPE</span></span>|<span data-ttu-id="7ac87-374">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-374">Int32</span></span>|  
|<span data-ttu-id="7ac87-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-375">TYPE_GUID</span></span>|<span data-ttu-id="7ac87-376">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-376">Guid</span></span>|  
|<span data-ttu-id="7ac87-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7ac87-378">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-378">Int64</span></span>|  
|<span data-ttu-id="7ac87-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7ac87-380">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-380">Int64</span></span>|  
|<span data-ttu-id="7ac87-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7ac87-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7ac87-382">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-382">Int32</span></span>|  
|<span data-ttu-id="7ac87-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7ac87-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="7ac87-384">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-384">Int16</span></span>|  
|<span data-ttu-id="7ac87-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7ac87-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="7ac87-386">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-386">Int64</span></span>|  
|<span data-ttu-id="7ac87-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7ac87-388">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-388">String</span></span>|  
|<span data-ttu-id="7ac87-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7ac87-390">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-390">String</span></span>|  
|<span data-ttu-id="7ac87-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7ac87-392">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-392">String</span></span>|  
|<span data-ttu-id="7ac87-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="7ac87-394">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-394">String</span></span>|  
|<span data-ttu-id="7ac87-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7ac87-396">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-396">String</span></span>|  
|<span data-ttu-id="7ac87-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-397">COLLATION_NAME</span></span>|<span data-ttu-id="7ac87-398">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-398">String</span></span>|  
|<span data-ttu-id="7ac87-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7ac87-400">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-400">String</span></span>|  
|<span data-ttu-id="7ac87-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7ac87-402">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-402">String</span></span>|  
|<span data-ttu-id="7ac87-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-403">DOMAIN_NAME</span></span>|<span data-ttu-id="7ac87-404">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-404">String</span></span>|  
|<span data-ttu-id="7ac87-405">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-405">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-406">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7ac87-407">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7ac87-407">Procedures</span></span>  
  
|<span data-ttu-id="7ac87-408">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-408">ColumnName</span></span>|<span data-ttu-id="7ac87-409">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7ac87-411">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-411">String</span></span>|  
|<span data-ttu-id="7ac87-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7ac87-413">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-413">String</span></span>|  
|<span data-ttu-id="7ac87-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="7ac87-415">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-415">String</span></span>|  
|<span data-ttu-id="7ac87-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7ac87-417">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-417">Int16</span></span>|  
|<span data-ttu-id="7ac87-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7ac87-419">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-419">String</span></span>|  
|<span data-ttu-id="7ac87-420">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-420">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-421">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-421">String</span></span>|  
|<span data-ttu-id="7ac87-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-422">DATE_CREATED</span></span>|<span data-ttu-id="7ac87-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-423">DateTime</span></span>|  
|<span data-ttu-id="7ac87-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7ac87-424">DATE_MODIFIED</span></span>|<span data-ttu-id="7ac87-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="7ac87-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="7ac87-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="7ac87-427">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-427">ColumnName</span></span>|<span data-ttu-id="7ac87-428">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7ac87-430">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-430">String</span></span>|  
|<span data-ttu-id="7ac87-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7ac87-432">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-432">String</span></span>|  
|<span data-ttu-id="7ac87-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="7ac87-434">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-434">String</span></span>|  
|<span data-ttu-id="7ac87-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-435">COLUMN_NAME</span></span>|<span data-ttu-id="7ac87-436">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-436">String</span></span>|  
|<span data-ttu-id="7ac87-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-437">COLUMN_GUID</span></span>|<span data-ttu-id="7ac87-438">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-438">Guid</span></span>|  
|<span data-ttu-id="7ac87-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-439">COLUMN_PROPID</span></span>|<span data-ttu-id="7ac87-440">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-440">Int64</span></span>|  
|<span data-ttu-id="7ac87-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="7ac87-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="7ac87-442">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-442">Int64</span></span>|  
|<span data-ttu-id="7ac87-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="7ac87-444">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-444">Int64</span></span>|  
|<span data-ttu-id="7ac87-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7ac87-445">IS_NULLABLE</span></span>|<span data-ttu-id="7ac87-446">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-446">Boolean</span></span>|  
|<span data-ttu-id="7ac87-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-447">DATA_TYPE</span></span>|<span data-ttu-id="7ac87-448">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-448">Int32</span></span>|  
|<span data-ttu-id="7ac87-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-449">TYPE_GUID</span></span>|<span data-ttu-id="7ac87-450">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-450">Guid</span></span>|  
|<span data-ttu-id="7ac87-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7ac87-452">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-452">Int64</span></span>|  
|<span data-ttu-id="7ac87-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7ac87-454">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-454">Int64</span></span>|  
|<span data-ttu-id="7ac87-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7ac87-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7ac87-456">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-456">Int32</span></span>|  
|<span data-ttu-id="7ac87-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7ac87-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="7ac87-458">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-458">Int16</span></span>|  
|<span data-ttu-id="7ac87-459">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-459">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-460">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-460">String</span></span>|  
|<span data-ttu-id="7ac87-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="7ac87-461">OVERLOAD</span></span>|<span data-ttu-id="7ac87-462">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="7ac87-463">Ansichten</span><span class="sxs-lookup"><span data-stu-id="7ac87-463">Views</span></span>  
  
|<span data-ttu-id="7ac87-464">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-464">ColumnName</span></span>|<span data-ttu-id="7ac87-465">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-466">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-467">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-467">String</span></span>|  
|<span data-ttu-id="7ac87-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-469">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-469">String</span></span>|  
|<span data-ttu-id="7ac87-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-470">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-471">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-471">String</span></span>|  
|<span data-ttu-id="7ac87-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="7ac87-473">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-473">String</span></span>|  
|<span data-ttu-id="7ac87-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="7ac87-474">CHECK_OPTION</span></span>|<span data-ttu-id="7ac87-475">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-475">Boolean</span></span>|  
|<span data-ttu-id="7ac87-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="7ac87-476">IS_UPDATABLE</span></span>|<span data-ttu-id="7ac87-477">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-477">Boolean</span></span>|  
|<span data-ttu-id="7ac87-478">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-478">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-479">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-479">String</span></span>|  
|<span data-ttu-id="7ac87-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-480">DATE_CREATED</span></span>|<span data-ttu-id="7ac87-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-481">DateTime</span></span>|  
|<span data-ttu-id="7ac87-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7ac87-482">DATE_MODIFIED</span></span>|<span data-ttu-id="7ac87-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7ac87-484">Indizes</span><span class="sxs-lookup"><span data-stu-id="7ac87-484">Indexes</span></span>  
  
|<span data-ttu-id="7ac87-485">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-485">ColumnName</span></span>|<span data-ttu-id="7ac87-486">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-487">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-488">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-488">String</span></span>|  
|<span data-ttu-id="7ac87-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-490">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-490">String</span></span>|  
|<span data-ttu-id="7ac87-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-491">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-492">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-492">String</span></span>|  
|<span data-ttu-id="7ac87-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-493">INDEX_CATALOG</span></span>|<span data-ttu-id="7ac87-494">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-494">String</span></span>|  
|<span data-ttu-id="7ac87-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="7ac87-496">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-496">String</span></span>|  
|<span data-ttu-id="7ac87-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-497">INDEX_NAME</span></span>|<span data-ttu-id="7ac87-498">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-498">String</span></span>|  
|<span data-ttu-id="7ac87-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7ac87-499">PRIMARY_KEY</span></span>|<span data-ttu-id="7ac87-500">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-500">Boolean</span></span>|  
|<span data-ttu-id="7ac87-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7ac87-501">UNIQUE</span></span>|<span data-ttu-id="7ac87-502">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-502">Boolean</span></span>|  
|<span data-ttu-id="7ac87-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7ac87-503">CLUSTERED</span></span>|<span data-ttu-id="7ac87-504">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-504">Boolean</span></span>|  
|<span data-ttu-id="7ac87-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-505">TYPE</span></span>|<span data-ttu-id="7ac87-506">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-506">Int32</span></span>|  
|<span data-ttu-id="7ac87-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7ac87-507">FILL_FACTOR</span></span>|<span data-ttu-id="7ac87-508">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-508">Int32</span></span>|  
|<span data-ttu-id="7ac87-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7ac87-509">INITIAL_SIZE</span></span>|<span data-ttu-id="7ac87-510">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-510">Int32</span></span>|  
|<span data-ttu-id="7ac87-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="7ac87-511">NULLS</span></span>|<span data-ttu-id="7ac87-512">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-512">Int32</span></span>|  
|<span data-ttu-id="7ac87-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7ac87-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7ac87-514">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-514">Boolean</span></span>|  
|<span data-ttu-id="7ac87-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7ac87-515">AUTO_UPDATE</span></span>|<span data-ttu-id="7ac87-516">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-516">Boolean</span></span>|  
|<span data-ttu-id="7ac87-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7ac87-517">NULL_COLLATION</span></span>|<span data-ttu-id="7ac87-518">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-518">Int32</span></span>|  
|<span data-ttu-id="7ac87-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="7ac87-520">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-520">Int64</span></span>|  
|<span data-ttu-id="7ac87-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-521">COLUMN_NAME</span></span>|<span data-ttu-id="7ac87-522">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-522">String</span></span>|  
|<span data-ttu-id="7ac87-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-523">COLUMN_GUID</span></span>|<span data-ttu-id="7ac87-524">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-524">Guid</span></span>|  
|<span data-ttu-id="7ac87-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-525">COLUMN_PROPID</span></span>|<span data-ttu-id="7ac87-526">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-526">Int64</span></span>|  
|<span data-ttu-id="7ac87-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7ac87-527">COLLATION</span></span>|<span data-ttu-id="7ac87-528">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-528">Int16</span></span>|  
|<span data-ttu-id="7ac87-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7ac87-529">CARDINALITY</span></span>|<span data-ttu-id="7ac87-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="7ac87-530">Decimal</span></span>|  
|<span data-ttu-id="7ac87-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="7ac87-531">PAGES</span></span>|<span data-ttu-id="7ac87-532">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-532">Int32</span></span>|  
|<span data-ttu-id="7ac87-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-533">FILTER_CONDITION</span></span>|<span data-ttu-id="7ac87-534">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-534">String</span></span>|  
|<span data-ttu-id="7ac87-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-535">INTEGRATED</span></span>|<span data-ttu-id="7ac87-536">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="7ac87-537">Microsoft Jet OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="7ac87-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="7ac87-538">Der Microsoft Jet OLE DB-Treiber unterstützt neben den allgemeinen Schemaauflistungen auch die folgenden spezifischen Schemaauflistungen:</span><span class="sxs-lookup"><span data-stu-id="7ac87-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="7ac87-539">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7ac87-539">Tables</span></span>  
  
- <span data-ttu-id="7ac87-540">Spalten</span><span class="sxs-lookup"><span data-stu-id="7ac87-540">Columns</span></span>  
  
- <span data-ttu-id="7ac87-541">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7ac87-541">Procedures</span></span>  
  
- <span data-ttu-id="7ac87-542">Ansichten</span><span class="sxs-lookup"><span data-stu-id="7ac87-542">Views</span></span>  
  
- <span data-ttu-id="7ac87-543">Indizes</span><span class="sxs-lookup"><span data-stu-id="7ac87-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="7ac87-544">Tabellen</span><span class="sxs-lookup"><span data-stu-id="7ac87-544">Tables</span></span>  
  
|<span data-ttu-id="7ac87-545">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-545">ColumnName</span></span>|<span data-ttu-id="7ac87-546">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-547">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-548">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-548">String</span></span>|  
|<span data-ttu-id="7ac87-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-550">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-550">String</span></span>|  
|<span data-ttu-id="7ac87-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-551">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-552">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-552">String</span></span>|  
|<span data-ttu-id="7ac87-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-553">TABLE_TYPE</span></span>|<span data-ttu-id="7ac87-554">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-554">String</span></span>|  
|<span data-ttu-id="7ac87-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-555">TABLE_GUID</span></span>|<span data-ttu-id="7ac87-556">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-556">Guid</span></span>|  
|<span data-ttu-id="7ac87-557">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-557">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-558">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-558">String</span></span>|  
|<span data-ttu-id="7ac87-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-559">TABLE_PROPID</span></span>|<span data-ttu-id="7ac87-560">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-560">Int64</span></span>|  
|<span data-ttu-id="7ac87-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-561">DATE_CREATED</span></span>|<span data-ttu-id="7ac87-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-562">DateTime</span></span>|  
|<span data-ttu-id="7ac87-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7ac87-563">DATE_MODIFIED</span></span>|<span data-ttu-id="7ac87-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="7ac87-565">Spalten</span><span class="sxs-lookup"><span data-stu-id="7ac87-565">Columns</span></span>  
  
|<span data-ttu-id="7ac87-566">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-566">ColumnName</span></span>|<span data-ttu-id="7ac87-567">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-568">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-569">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-569">String</span></span>|  
|<span data-ttu-id="7ac87-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-571">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-571">String</span></span>|  
|<span data-ttu-id="7ac87-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-572">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-573">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-573">String</span></span>|  
|<span data-ttu-id="7ac87-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-574">COLUMN_NAME</span></span>|<span data-ttu-id="7ac87-575">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-575">String</span></span>|  
|<span data-ttu-id="7ac87-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-576">COLUMN_GUID</span></span>|<span data-ttu-id="7ac87-577">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-577">Guid</span></span>|  
|<span data-ttu-id="7ac87-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-578">COLUMN_PROPID</span></span>|<span data-ttu-id="7ac87-579">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-579">Int64</span></span>|  
|<span data-ttu-id="7ac87-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="7ac87-581">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-581">Int64</span></span>|  
|<span data-ttu-id="7ac87-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="7ac87-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="7ac87-583">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-583">Boolean</span></span>|  
|<span data-ttu-id="7ac87-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="7ac87-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="7ac87-585">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-585">String</span></span>|  
|<span data-ttu-id="7ac87-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7ac87-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="7ac87-587">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-587">Int64</span></span>|  
|<span data-ttu-id="7ac87-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="7ac87-588">IS_NULLABLE</span></span>|<span data-ttu-id="7ac87-589">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-589">Boolean</span></span>|  
|<span data-ttu-id="7ac87-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-590">DATA_TYPE</span></span>|<span data-ttu-id="7ac87-591">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-591">Int32</span></span>|  
|<span data-ttu-id="7ac87-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-592">TYPE_GUID</span></span>|<span data-ttu-id="7ac87-593">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-593">Guid</span></span>|  
|<span data-ttu-id="7ac87-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="7ac87-595">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-595">Int64</span></span>|  
|<span data-ttu-id="7ac87-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="7ac87-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="7ac87-597">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-597">Int64</span></span>|  
|<span data-ttu-id="7ac87-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7ac87-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="7ac87-599">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-599">Int32</span></span>|  
|<span data-ttu-id="7ac87-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="7ac87-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="7ac87-601">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-601">Int16</span></span>|  
|<span data-ttu-id="7ac87-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="7ac87-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="7ac87-603">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-603">Int64</span></span>|  
|<span data-ttu-id="7ac87-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="7ac87-605">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-605">String</span></span>|  
|<span data-ttu-id="7ac87-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="7ac87-607">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-607">String</span></span>|  
|<span data-ttu-id="7ac87-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="7ac87-609">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-609">String</span></span>|  
|<span data-ttu-id="7ac87-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="7ac87-611">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-611">String</span></span>|  
|<span data-ttu-id="7ac87-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="7ac87-613">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-613">String</span></span>|  
|<span data-ttu-id="7ac87-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-614">COLLATION_NAME</span></span>|<span data-ttu-id="7ac87-615">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-615">String</span></span>|  
|<span data-ttu-id="7ac87-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="7ac87-617">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-617">String</span></span>|  
|<span data-ttu-id="7ac87-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="7ac87-619">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-619">String</span></span>|  
|<span data-ttu-id="7ac87-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-620">DOMAIN_NAME</span></span>|<span data-ttu-id="7ac87-621">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-621">String</span></span>|  
|<span data-ttu-id="7ac87-622">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-622">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-623">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="7ac87-624">Verfahren</span><span class="sxs-lookup"><span data-stu-id="7ac87-624">Procedures</span></span>  
  
|<span data-ttu-id="7ac87-625">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-625">ColumnName</span></span>|<span data-ttu-id="7ac87-626">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="7ac87-628">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-628">String</span></span>|  
|<span data-ttu-id="7ac87-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="7ac87-630">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-630">String</span></span>|  
|<span data-ttu-id="7ac87-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="7ac87-632">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-632">String</span></span>|  
|<span data-ttu-id="7ac87-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="7ac87-634">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-634">Int16</span></span>|  
|<span data-ttu-id="7ac87-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="7ac87-636">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-636">String</span></span>|  
|<span data-ttu-id="7ac87-637">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-637">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-638">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-638">String</span></span>|  
|<span data-ttu-id="7ac87-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-639">DATE_CREATED</span></span>|<span data-ttu-id="7ac87-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-640">DateTime</span></span>|  
|<span data-ttu-id="7ac87-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7ac87-641">DATE_MODIFIED</span></span>|<span data-ttu-id="7ac87-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="7ac87-643">Ansichten</span><span class="sxs-lookup"><span data-stu-id="7ac87-643">Views</span></span>  
  
|<span data-ttu-id="7ac87-644">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-644">ColumnName</span></span>|<span data-ttu-id="7ac87-645">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-646">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-647">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-647">String</span></span>|  
|<span data-ttu-id="7ac87-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-649">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-649">String</span></span>|  
|<span data-ttu-id="7ac87-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-650">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-651">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-651">String</span></span>|  
|<span data-ttu-id="7ac87-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="7ac87-653">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-653">String</span></span>|  
|<span data-ttu-id="7ac87-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="7ac87-654">CHECK_OPTION</span></span>|<span data-ttu-id="7ac87-655">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-655">Boolean</span></span>|  
|<span data-ttu-id="7ac87-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="7ac87-656">IS_UPDATABLE</span></span>|<span data-ttu-id="7ac87-657">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-657">Boolean</span></span>|  
|<span data-ttu-id="7ac87-658">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7ac87-658">DESCRIPTION</span></span>|<span data-ttu-id="7ac87-659">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-659">String</span></span>|  
|<span data-ttu-id="7ac87-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-660">DATE_CREATED</span></span>|<span data-ttu-id="7ac87-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-661">DateTime</span></span>|  
|<span data-ttu-id="7ac87-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="7ac87-662">DATE_MODIFIED</span></span>|<span data-ttu-id="7ac87-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="7ac87-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="7ac87-664">Indizes</span><span class="sxs-lookup"><span data-stu-id="7ac87-664">Indexes</span></span>  
  
|<span data-ttu-id="7ac87-665">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="7ac87-665">ColumnName</span></span>|<span data-ttu-id="7ac87-666">DataType</span><span class="sxs-lookup"><span data-stu-id="7ac87-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="7ac87-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-667">TABLE_CATALOG</span></span>|<span data-ttu-id="7ac87-668">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-668">String</span></span>|  
|<span data-ttu-id="7ac87-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="7ac87-670">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-670">String</span></span>|  
|<span data-ttu-id="7ac87-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-671">TABLE_NAME</span></span>|<span data-ttu-id="7ac87-672">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-672">String</span></span>|  
|<span data-ttu-id="7ac87-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="7ac87-673">INDEX_CATALOG</span></span>|<span data-ttu-id="7ac87-674">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-674">String</span></span>|  
|<span data-ttu-id="7ac87-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="7ac87-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="7ac87-676">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-676">String</span></span>|  
|<span data-ttu-id="7ac87-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-677">INDEX_NAME</span></span>|<span data-ttu-id="7ac87-678">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-678">String</span></span>|  
|<span data-ttu-id="7ac87-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="7ac87-679">PRIMARY_KEY</span></span>|<span data-ttu-id="7ac87-680">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-680">Boolean</span></span>|  
|<span data-ttu-id="7ac87-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="7ac87-681">UNIQUE</span></span>|<span data-ttu-id="7ac87-682">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-682">Boolean</span></span>|  
|<span data-ttu-id="7ac87-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="7ac87-683">CLUSTERED</span></span>|<span data-ttu-id="7ac87-684">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-684">Boolean</span></span>|  
|<span data-ttu-id="7ac87-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="7ac87-685">TYPE</span></span>|<span data-ttu-id="7ac87-686">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-686">Int32</span></span>|  
|<span data-ttu-id="7ac87-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="7ac87-687">FILL_FACTOR</span></span>|<span data-ttu-id="7ac87-688">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-688">Int32</span></span>|  
|<span data-ttu-id="7ac87-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="7ac87-689">INITIAL_SIZE</span></span>|<span data-ttu-id="7ac87-690">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-690">Int32</span></span>|  
|<span data-ttu-id="7ac87-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="7ac87-691">NULLS</span></span>|<span data-ttu-id="7ac87-692">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-692">Int32</span></span>|  
|<span data-ttu-id="7ac87-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="7ac87-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="7ac87-694">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-694">Boolean</span></span>|  
|<span data-ttu-id="7ac87-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="7ac87-695">AUTO_UPDATE</span></span>|<span data-ttu-id="7ac87-696">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-696">Boolean</span></span>|  
|<span data-ttu-id="7ac87-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="7ac87-697">NULL_COLLATION</span></span>|<span data-ttu-id="7ac87-698">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-698">Int32</span></span>|  
|<span data-ttu-id="7ac87-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="7ac87-700">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-700">Int64</span></span>|  
|<span data-ttu-id="7ac87-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="7ac87-701">COLUMN_NAME</span></span>|<span data-ttu-id="7ac87-702">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-702">String</span></span>|  
|<span data-ttu-id="7ac87-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-703">COLUMN_GUID</span></span>|<span data-ttu-id="7ac87-704">GUID</span><span class="sxs-lookup"><span data-stu-id="7ac87-704">Guid</span></span>|  
|<span data-ttu-id="7ac87-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="7ac87-705">COLUMN_PROPID</span></span>|<span data-ttu-id="7ac87-706">Int64</span><span class="sxs-lookup"><span data-stu-id="7ac87-706">Int64</span></span>|  
|<span data-ttu-id="7ac87-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="7ac87-707">COLLATION</span></span>|<span data-ttu-id="7ac87-708">Int16</span><span class="sxs-lookup"><span data-stu-id="7ac87-708">Int16</span></span>|  
|<span data-ttu-id="7ac87-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="7ac87-709">CARDINALITY</span></span>|<span data-ttu-id="7ac87-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="7ac87-710">Decimal</span></span>|  
|<span data-ttu-id="7ac87-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="7ac87-711">PAGES</span></span>|<span data-ttu-id="7ac87-712">Int32</span><span class="sxs-lookup"><span data-stu-id="7ac87-712">Int32</span></span>|  
|<span data-ttu-id="7ac87-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="7ac87-713">FILTER_CONDITION</span></span>|<span data-ttu-id="7ac87-714">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="7ac87-714">String</span></span>|  
|<span data-ttu-id="7ac87-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="7ac87-715">INTEGRATED</span></span>|<span data-ttu-id="7ac87-716">Boolesch</span><span class="sxs-lookup"><span data-stu-id="7ac87-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7ac87-717">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ac87-717">See also</span></span>

- [<span data-ttu-id="7ac87-718">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="7ac87-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
