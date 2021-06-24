FROM node

RUN wget -O /usr/local/bin/gitlab-runner https://gitlab-ci-multi-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-ci-multi-runner-linux-amd64 && \
    chmod +x /usr/local/bin/gitlab-runner && \
    useradd --comment 'GitLab Runner' --create-home gitlab-runner --shell /bin/bash && \
    npm install -g typescript

CMD gitlab-runner register \
    	-u http://gitlab/ci \
    	-r rSyUTfHxLL_qP7nYSfvA \
    	-n \
    	--executor shell \
    	--tag-list "typescript"\
    	--name "TypeScript Runner" && \
    gitlab-runner install --user=gitlab-runner --working-directory=/home/gitlab-runner && \
    gitlab-runner start && \
    tail -f /var/log/dpkg.log
