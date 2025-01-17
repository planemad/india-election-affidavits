# india-election-affidavits

Dataset of candidate affidavits filed during elections. Sourced from [MyNeta](https://myneta.info/), an open data repository platform of [Association for Democratic Reforms (ADR)](https://adrindia.org). Information submitted by candidates in their affidavits are not guaranteed to match reality.

Browse the dataset here: <https://flatgithub.com/Vonter/india-election-affidavits?filename=csv/Lok%20Sabha/Candidates.csv&stickyColumnName=Candidate>.

## Scripts

- [fetch.sh](fetch.sh): Fetches the raw HTML pages from [MyNeta](https://myneta.info/)
- [flatten.py](flatten.py): Parses the raw HTML pages, and generates the CSV dataset
- [append.py](append.py): Extends the base CSV dataset with additional columns

## Extended

The base CSV dataset has been extended with additional columns - for integrating with other datasets:
- [shapefile.csv](extended/shapefile.csv): `pc_id` column for mapping to [Parliamentary Constituencies Shapefile (2019)](https://github.com/datameet/maps/blob/master/parliamentary-constituencies/india_pc_2019_simplified.geojson)

## License

This india-election-affidavits dataset is made available under the Open Database License: http://opendatacommons.org/licenses/odbl/1.0/. 
Users of this data should attribute Association for Democratic Reforms (ADR): https://adrindia.org

You are free:

* **To share**: To copy, distribute and use the database.
* **To create**: To produce works from the database.
* **To adapt**: To modify, transform and build upon the database.

As long as you:

* **Attribute**: You must attribute any public use of the database, or works produced from the database, in the manner specified in the ODbL. For any use or redistribution of the database, or works produced from it, you must make clear to others the license of the database and keep intact any notices on the original database.
* **Share-Alike**: If you publicly use any adapted version of this database, or works produced from an adapted database, you must also offer that adapted database under the ODbL.
* **Keep open**: If you redistribute the database, or an adapted version of it, then you may use technological measures that restrict the work (such as DRM) as long as you also redistribute a version without such measures.

## Generating

Ensure you have `bash`, `curl` and `python` installed

```
# Fetch the data
bash fetch.sh

# Generate the CSV
python flatten.py

# Include additional columns
python append.py
```

The fetch script sources data from MyNeta (https://myneta.info/)

## TODO

- State Assemblies
- Local Bodies
- Rajya Sabha
- Election Expenses
- Detailed affidavit information

## Credits

- [MyNeta](https://myneta.info/)
- [Association for Democratic Reforms (ADR)](https://adrindia.org)

## Related

- [Parliamentary Constituencies Shapefile (2019)](https://github.com/datameet/maps/blob/master/parliamentary-constituencies/india_pc_2019_simplified.geojson) ([thanks to @planemad for the `pc_id` mapping](https://github.com/Vonter/india-election-affidavits/issues/1#issue-2132946129))
