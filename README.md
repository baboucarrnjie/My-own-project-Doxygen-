% Postprocess
htmlDir = outdir;
if exist(fullfile(htmlDir,’index.html’),’file’)~=2
htmlDir = [outdir,filesep,’html’];
end
fprintf(’running mtoc++ postprocessor...’);
[~,postwarn] = system(sprintf(’%smtocpp_post "%s" 1>%s’,...
ldpath,htmlDir, strs.null));
if ~isempty(postwarn)
warn = [warn sprintf(’mtoc++ postprocessor messages:\n’)...
postwarn];
end# My-own-project-Doxygen-
