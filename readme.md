git clone https://github.com/SAP/spartacus.git && cd spartacus

git checkout release/5.0.0-CF1

npm install && npm run build:libs

cd ..

find spartacus/feature-libs/. -type d -maxdepth 1 -mindepth 1 -exec bash -c "cd {} && npm pack && mv *.tgz ../../../" \;
