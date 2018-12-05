
.PHONY: all clean

all: KEN_ALL.CSV JIGYOSYO.CSV
	perl ./csv2jsonzip.pl KEN_ALL.CSV JIGYOSYO.CSV
	for file in ../zipdata/*.json; do \
		echo "Normalize $$file" ; \
		cat ../zipdata/$$file | jq -S -c -M -j . | sponge ../zipdata/$$file ; \
	done

KEN_ALL.CSV: ken_all.zip
	unzip -o ken_all.zip

ken_all.zip:
	curl https://www.post.japanpost.jp/zipcode/dl/kogaki/zip/ken_all.zip > ken_all.zip

JIGYOSYO.CSV: jigyosyo.zip 
	unzip -o jigyosyo.zip

jigyosyo.zip:
	curl https://www.post.japanpost.jp/zipcode/dl/jigyosyo/zip/jigyosyo.zip > jigyosyo.zip

clean:
	rm KEN_ALL.CSV ken_all.zip JIGYOSYO.CSV jigyosyo.zip
