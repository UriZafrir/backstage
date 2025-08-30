<!-- on root
yarn tsc
then
cd plugins/kubernetes-backend/
yarn install ?
yarn build
#load env variables from .env with export
npm publish -->

#from root:
yarn install
yarn workspace @backstage/plugin-kubernetes-backend build
cd plugins/kubernetes-backend
#replace
sed -i 's/"@backstage\/plugin-kubernetes-backend"/"@urizafrir\/plugin-kubernetes-backend"/' package.json
export .env
npm publish --access public
#replace again
sed -i 's/"@urizafrir\/plugin-kubernetes-backend"/"@backstage\/plugin-kubernetes-backend"/' package.json
